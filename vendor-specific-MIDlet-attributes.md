# Vendor-specific MIDlet attributes

### Nokia
#### Series 60
| Attribute | Description | Values
| ------------ | ------------ | ------------
| Nokia-MIDlet-Category | Destination folder for MIDlet installation. _Since: S60 2nd Edition_ | `Application` , `Game`
| Nokia-MIDlet-Original-Display-Size | Specifies the screen for which the MIDlet was designed. This is used to adapt the MIDlet for full-screen mode on a mobile device. Scaling applies to full screen LCDUI Canvases only. _Since: S60 3rd Edition_ | `(Width),(Height)`
|  Nokia-MIDlet-Target-Display-Size | Specifies the target size for the MIDlet. This usually same as target device’s screen size. This attribute is usually used in conjunction with `Nokia-MIDlet-Original-Display-Size`. Scaling applies to full screen LCDUI Canvases only. _Since: S60 3rd Edition_ |  `(Width),(Height)`
|  Nokia-Scalable-Icon  /  Nokia-Scalable-Icon-MIDlet-`(n)`  | Specifies scalable (SVG) MIDlet icon support. For MIDlet suites, the attribute `Nokia-Scalable-Icon-MIDlet-n` specifies the icon for MIDlet `n`. _Since: S60 3rd Edition FP 2_ | `(Scalable icon path)`
|  Nokia-MIDlet-UID-`(n)`  | Predefined UID for a MIDlet. UID can be from following ranges: Unprotected range 0xA0000000 - 0xAFFFFFFF , Protected range 0x20000000 - 0x2FFFFFFF , Test range 0xE0000000 - 0xEFFFFFFF. In the case the UID is from protected range, the MIDlet Suite must be signed and the UID must be specified in both the JAD and the JAR manifest file. _Since: S60 3rd Edition FP 2_ | `(range)`
|  Nokia-UI-Enhancement  | Comma separated list, where the following attributes are allowed: `CanvasHasBackground`: Displays the default theme background image as a normal mode Canvas (not full screen) component background instead of the default white background. If the MIDlet does not render all the pixels of a given clip region in the paint method, the theme background is shown. `MusicKeysSupported`: Allow acquisition of media key events from the MIDlet. `PopUpTextBox`: Sets TextBox as a pop-up TextBox. `FullScreenTextBox`: Replaces the default pop-up TextBox with a full-screen TextBox. `IgnoreProfilesBasedSoundMuting`: Disabling automatic audio muting for the Meeting and Silent profiles.  _Since: S60 3rd Edition FP 2_ | `(attribute),(attribute),...` where valid attributes are: `CanvasHasBackground` ,  `MusicKeysSupported` , `PopUpTextBox` , `FullScreenTextBox` , `MusicKeysSupported`
|  Nokia-MIDlet-Canvas-Scaling-Orientation-Switch  | Specifies whether MIDlet allows change of original MIDlet size (`Nokia-MIDlet-Original-Display-Size`) orientation when switching from portrait to landscape mode. After resolution switch the MIDlet is notified via sizeChanged() function of LCDUI Canvas. `Nokia-MIDlet-Canvas-Scaling-Orientation-Switch` is always used together with `Nokia-MIDlet-Original-Display-Size`. As `Nokia-MIDlet-Original-Display-Size` is used to indicate a fixed resolution that full screen Canvas content of the MIDlet is designed for, then additionally specifying `Nokia-MIDlet-Canvas-Scaling-Orientation-Switch` to `true` indicates that the MIDlet can also support the given resolution in both portrait and landscape resolutions. Behavior of combining `Nokia-MIDlet-Canvas-Scaling-Orientation-Switch: true` and setting `Nokia-MIDlet-Target-Display-Size` is undefined. _Since: S60 3rd Edition FP 2_ | `true` , `false`
|  Nokia-MIDlet-No-Exit  | Prevents the MIDlet from closing via pressing the End key. Instead of closing the MIDlet it is put to the background. The MIDlet can be still closed from the list of open applications. _Since: S60 3rd Edition FP 2_ | `true` , `false`
|  Nokia-MIDlet-Flip-Close  | Specifies MIDlet behaviour on flip-close event. If value is pause, pauseApp() is called if flip is closed. If flip then is opened, startApp() is called. By default the attribute value is run and therefore pauseApp() and startApp() are not called when flip is closed. If MIDlet is already in background it does not get any notification about flip close event. _Since: S60 3rd Edition FP 2_ | `pause` , `run`
|  Nokia-MIDlet-Background-Event  | Specifies MIDlet behavior to background event. If value is `pause`, pauseApp() is called if on to background event takes place. If on to foreground event takes place, startApp() is called. By default the attribute value is `run` and therefore pauseApp() and startApp() are not called when on to background event takes place. _Since: S60 3rd Edition FP 2_ | `pause` , `run`
|  Nokia-MIDlet-Block-Uninstall  | Prevents uninstallation of the MIDlet Suite if value of this attribute is true. Only Manufacturer or Operator signed applications are able to use this attribute. This attribute must be specified in the JAR manifest file. _Since: S60 3rd Edition FP 2_ | `true` , `false`
| Nokia-MIDlet-S60-Selection-Key-Compatibility | This attribute changes the default Selection key behavior in Canvas and CustomItem elements. By default normal mode Canvas and CustomItem do not get low level key events even if there is no CommandListener defined. This attribute changes the default Selection key behaviour regarding Commands in normal mode Canvas and CustomItem. If value of attribute is true, no Commands are mapped to Selection key, instead the low level key event (-5) is triggered. Note that in a full screen mode Canvas without any Commands and CommandListener defined, this feature does not have any effect as low level key events are triggered from all softkeys in any case. _Since: S60 3rd Edition FP 2_ | `true` , `false`
| Nokia-Forward-Lock | Specifies whether the MIDlet suite in the MIDlet Message is installed as forward-locked. Forward-locked means that the MIDlet suite JAR file from the MIDlet Message is DRM-encrypted during installation. _Since: Symbian^3 (Java Runtime 2.1)_ | `true` , `false`
| Nokia-MIDlet-App-Orientation | Allows MIDlet to force either portrait or landscape UI orientation. The orientation is only fixed on devices that support the specific layout. _Since: S60 5th Edition_ | `portrait` , `landscape`
| Nokia-MIDlet-Delete-Confirm-`(locale)` | Specifies the localized confirmation prompt shown when the user selects to remove the MIDlet or MIDlet suite. _Since: Symbian^3 (Java Runtime 2.1)_ | `(message)`
| Nokia-MIDlet-Launch-Params | Specifies the set of parameters that the application supports when launched using launchapp: or javaapp: URI platform request. _Since: Symbian^3 (Java Runtime 2.1)_ | `(Comma separated list of property names)`
| Nokia-MIDlet-Name-`(locale)` | The localized name of the MIDlet suite for the specified `locale`. _Since: Symbian^3 (Java Runtime 2.1)_ | `(name)`
| Nokia-MIDlet-`(n)`-`(locale)` | The localized name of the MIDlet `n` of a MIDlet suite. _Since: Symbian^3 (Java Runtime 2.1)_ | `(name)`
|  Nokia-MIDlet-On-Screen-Keypad  | Specifies the on-screen keypad for a Canvas application. This attribute is valid only in touch-enabled devices that have limited physical key availability. _Since: S60 5th Edition_ | `no` , `gameactions` _(UP, DOWN, LEFT, RIGHT, FIRE, GAME_A, GAME_B GAME_C and GAME_D)_ , `navigationkeys` _(UP, DOWN, LEFT, RIGHT and FIRE)_
|  Nokia-MIDlet-On-Screen-Softkeys-Position  | Defines where softkeys are placed on the screen when using the on-screen keypad on devices that have no physical softkeys. _Since: S60 5th Edition (Java Runtime 1.4)_ | `right` , `bottom`
|  Nokia-MIDlet-Splash-Screen-Image | Defines the custom start-up screen ("splash screen") used by the MIDlet. This attribute can also be used to define multiple custom start-up screens for the device to choose from or to disable ("suppress") the start-up screen for the MIDlet. _Since: Symbian^3 (Java Runtime 2.1)_ | `(image),(image),...` , `suppress`
|  Nokia-MIDlet-Tap-Detection-Options  | Sets the size of tap detection area and tap time-out on Touch UI devices. If the pointer stays pressed within the detection area and does not surpass the time-out value, the event is considered a single tap. If the pointer leaves the detection area or the time-out passes, drag events start being generated. The detection area is a rectangle, measured in twips. The entered value is half the length of one side of the rectangle. _Since: S60 5th Edition (Java Runtime 1.4)_ | `(detection rectangle size),(timeout)`

#### Examples:
```
Nokia-MIDlet-Category: Application
Nokia-MIDlet-Original-Display-Size: 176,208
Nokia-MIDlet-Target-Display-Size: 240,320
Nokia-Scalable-Icon: /icons/gamesuite.svg
Nokia-Scalable-Icon-MIDlet-1: /icons/gamesuite1.svg
Nokia-Scalable-Icon-MIDlet-2: /icons/gamesuite2.svg
Nokia-MIDlet-UID-1: 0xE0000000
Nokia-MIDlet-UID-2: 0xE0000001
Nokia-UI-Enhancement: CanvasHasBackground
Nokia-MIDlet-Canvas-Scaling-Orientation-Switch: true
Nokia-MIDlet-Flip-Close: pause
Nokia-MIDlet-App-Orientation: landscape
Nokia-MIDlet-Launch-Params: sounds,difficulty,wizard_mode
Nokia-MIDlet-Name-es-MX: HolaMundo
Nokia-MIDlet-2-en-GB: HelloWorld
Nokia-MIDlet-On-Screen-Keypad: gameactions
Nokia-MIDlet-Splash-Screen-Image: portrait_300x600.jpg, landscape_600x300.jpg, splash_300x300.png
Nokia-MIDlet-Splash-Screen-Image: suppress
Nokia-MIDlet-Delete-Confirm-en: Are you sure you want to delete this MIDlet?
Nokia-UI-Enhancement: CanvasHasBackground,MusicKeysSupported
```

#### Series 40

| Attribute | Description | Values
| ------------ | ------------ | ------------
| Nokia-Update | MIDlet Version update URL | `(url)`
| Nokia-MIDlet-national-digit-display | Used to enable national rather than Latin digit display. _Since: Series 40 5th Edition_ | `true` , `false`
| Nokia-MIDlet-Background-Exit-Confirm-`(locale)` | Prompt to use in a confirmation before stopping a background MIDlet prior when freeing heap space. _Since: Series 40 6th Edition_ | `(message)`
| Nokia-MIDlet-bg-launchpad | Indicates MIDlet-`n` in the suite that is a launchpad MIDlet (JAR explorer). _Since: Series 40 5th Edition FP 1_ | `n`
| Nokia-MIDlet-bg-memory-size | Indicates that the MIDlet can run in the background and defines the amount of heap it is allowed in the background in kb. _Since: Series 40 3rd Edition FP 2_  | `(kb)`
| Nokia-MIDlet-bg-server | Indicates MIDlet-`n` in the suite that is a BG server. _Since: Series 40 5th Edition FP 1_ | `(n)`
| Nokia-MIDlet-bg-user-disable | Indicates if the MIDlet can be stopped by the user to free background heap for another MIDlet to start. _Since: Series 40 5th Edition FP 1_ | `true` , `false`
| Nokia-MIDlet-Category | Used to determine the folder to which MIDlets are stored following an OTA Download. Special values: `IdleScreen`: Identifies a MIDlet that is capable of displaying content on the idle screen. `PassiveIdleScreen`: Identifies a MIDlet that is capable of running as an idle skin application (taking over the whole main zone). `Search`: Identifies a MIDlet that provides search capabilities used by a native idle search application.  _Since: Series 40 6th Edition_ | `Application` , `Commerce` , `Game` , `Messaging` , `Screensaver` , `IdleScreen` , `PassiveIdleScreen` , `Search`
| Nokia-MIDlet-Close-Gprs-Context | If set to true, after all HTTP connections are closed, there is a time-out of 10 seconds before shutting down GPRS context . By default there is no time out, which means the GPRS context will be kept till the MIDlet exits. _Since: Series 40 5th Edition FP 1_ | `true` , `false`
| Nokia-MIDlet-Connectionsettings  | Provides an identifier string for provisioned connection settings. It specifies provisioned proxy or access point settings to be used when the MIDlet is accessing the network (over HTTP or TCP/UDP). The given identifier provides one-to-one mapping to the connection settings. The identifier has to conform with OMA DM and WAP Provisioning standards. The identifier strings are specific to the manufacturer or operator. _Since: Series 40 6th Edition Lite_ | `(identifier)`
| Nokia-MIDlet-Name-`(locale)` | The localized name of the MIDlet suite for the specified `locale`. _Since: Series 40 3rd Edition_ | `(name)`
| Nokia-MIDlet-Name-`(n)`-`(locale)` | The localized name of the MIDlet `n` of a MIDlet suite. _Since: Series 40 3rd Edition_ | `(name)`
| Nokia-MIDlet-no-exit | Indicates a MIDlet that cannot exit once started. _Since: Series 40 3rd Edition FP 2_ | `true` , `false`
| Nokia-MIDlet-Save-Location | Used to determine download folder (currently only supports the root (predefjava) folder). _Since: Series 40 5th Edition FP 1_ | `Root`
| Nokia-Service | Used to indicate an upload service. Upload services are downloaded with different UI to other MIDlets. _Since: Series 40 5th Edition FP 1_ | `true` , `false`
|  Nokia-UI-Enhancement  | Comma separated list, where the following attributes are allowed: `CanvasHasBackground`: Displays the default theme background image as a normal mode Canvas (not full screen) component background instead of the default white background. If the MIDlet does not render all the pixels of a given clip region in the paint method, the theme background is shown. `MusicKeysSupported`: Allow acquisition of media key events from the MIDlet. _Since: Series 40 3rd Edition_ | `(attribute),(attribute),...` where the valid attributes are: `CanvasHasBackground` , `MusicKeysSupported`
| Nokia-Update | Version update URL, used when doing Update Check. If no URL then Update Check is disabled. _Since: Series 40 3rd Edition_ | `(url)`
| progressive_download | Set to enabled to enable JSR-135 progressive playback. _Since: Series 40 3rd Edition FP 2_ | `enabled`
#### Notes
 - Background MIDlets are enabled only for operator and manufacturer domains.
- Nokia S40 phones return an error when unknown attributes starting with `MIDlet-` are found. So for example Samsung's `MIDlet-Touch-Support: True` attribute causes an error when triying to launch on a Nokia phone.
- `(locale)` is one of the following values:

```
S40 and Symbian

Arabic: ar
Basque: eu
Bulgarian: bg-BG
Catalan: ca
China: zh-CN
Croatian: hr-HR
Czech: cs-CZ
Danish: da-DK
Dutch: nl-NL
English: en
English (Taiwan): en
English (Japan): en
English (Hong Kong): en
English (PRC China): en
English (Thailand): en
English (US): en-US
Estonian: et-EE
Farsi: fa
Finnish: fi-FI
French: fr
French (Canadian): fr-CA
Galician: gl
German: de
Greek: el-GR
Hebrew: he-IL
Hindi: hi-IN
Hongkong: zh-HK
Hungarian: hu-HU
Icelandic: is-IS
Indonesian: id-ID
Italian: it
Japanese: ja-JP
Latvian: lv-LV
Lithuanian: lt-LT
Malay: ms-MY
Norwegian: no-NO
Polish: pl-PL
Portuguese: pt-PT
Portuguese (Brazilian): pt-BR
Romanian: ro-RO
Russian: ru-RU
Serbian: sr-YU
Slovak: sk-SK
Slovenian: sl-SI
Spanish: es-ES
Spanish (Latin America): es-US
Swedish: sv
Tagalog: tl-PH
Taiwan: zh-TW
Thai: th-TH
Turkish: tr-TR
Ukrainian: uk-UA
Urdu: ur
Vietnamese: vi-VN 

S40 only

Afrikaans: af-ZA
Albanian: sq
Amharic: am-ET
Armenian: hy
Assamese: as-IN
Azeri: az-AZ
Belarusian: be
Bengali: bn
Bengali_BD: bn-BD
Bosnian: bs-BA
Chinese (Traditional): zh-TW
Euskara: eu
Georgian: ka-GE
Gujarati: gu-IN
Hausa: ha
Igbo: ig-NG
Kannada: kn-IN
Kashmiri: ks-IN
Kazak: kk-KZ
Khmer: km-KH
Kirghiz: ky-KG
Lao: lo-LA
Lingala: ln
Macedonian: mk-MK
Malayalam: ml-IN
Marathi: mr-IN
Mongolian: mn-MN
Oriya: or-IN
Persian: fa-AF
Punjabi: pa
Pushto: ps
Sesotho: st
Sinhala: si-LK
Swahili: sw
Tamil: ta
Tajik: tg-TJ
Telugu: te-IN
Turkmen: tk
Uzbek: uz-UZ
Xhosa: xh
Yoruba: yo
Zulu: zu

Symbian only

Korean: ko-KR
```
#### Examples
```
Nokia-MIDlet-Background-Exit-Confirm-en : Don't stop me please
Nokia-MIDlet-bg-version: 1.0
Nokia-MIDlet-Connectionsettings: specialProxy
Nokia-MIDlet-1-en: Bounce
```

### Samsung
| Attribute | Description | Values
| ------------ | ------------ | ------------
|  MIDlet-Touch-Support  | Specifies whether the MIDlet supports touch events. Disables virtual keypads on some devices. | `true` , `false`
| MIDlet-Scaleup-Support  | Controls screen upscaling. | `true` , `false`
| MVM-Pause-Background | Enables running MIDlets on the background. Sound playback will stop. | `true` , `false`
| Content-Folder | Folder where the downloaded MIDlet should be stored | `(path)` , example: ` file:///CFCard/ `
| Complete- Launch-Label  / Complete-Web-Label |  The character string indicated in this attribute is to be used for the  download  complete screen. This is primarily used to initiate a launch request. | `(label)`
| Content-Forward-Lock | If set to `NO` , the MIDlet can be sent to other devices. If not specified, the MIDlet is locked by default | `NO`
| Content-ID |  Identifier for the content so that it can be launched from outside the AMS. | `(string)`
|  Content-DRM-Cancel-URL / Content-DRM-Check-URL / Content-DRM-Renew-URL | URL to cancel, check and renew DRM rights | `(url)`
| Content-DRM-Until | It is used to specify DRM support time to the specific product. Date is represented as defined by HTTP/1.1 (RFC 2616) | `(datetime)` , example: `Wed, 22 Nov 2011 01:01:01 GMT`
| Content-Run-Until | Date at which the user won't be allowed to access the MIDlet anymore. Date is represented as defined by HTTP/1.1 (RFC 2616) | `(datetime)` , example: `Wed, 18 Feb 2004 16:10 GMT `
| Content-Run-Count | Number of times the application may be launched on the device. Max. value supported is 99. | `n`

#### Attributes without proper official documentation found:
| Attribute | Description | Known values
| ------------ | ------------ | ------------
| MIDlet-ScreenMode | Enables screen rotation. | `ROTATE`
| MIDlet-Landscape-Support | MIDlet supports landscape orientation | `TRUE` , `FALSE`
| MVM-BGM-Support | _Unknown_ | `true` , `false`

### Examples:
```
MIDlet-Touch-Support: True
MIDlet-Scaleup-Support: false
Content-Folder: file:///CFCard/ 
```

### LG
| Attribute | Description | Values (default in bold)
| ------------ | ------------ | ------------
| LGE-MIDlet-Allowed-background | Allows MIDlet execution while multitasking. | `yes` , **`no`**
| LGE-MIDlet-Delete-Option / LGE-MIDlet-Undelete-Option | Specifies whether the user can delete the MIDlet. `LGE-MIDlet-Delete-Option` and `LGE-MIDlet-Undelete-Option` have opposite values | `yes` ,**`no`**
| 3G-MIDlet-Undeletable | Specifies whether the user can delete the MIDlet. | `yes` , **`no`**
| LGE-MIDlet-autolaunch-power-on | Specifies whether to launch the MIDlet when the phone is powered on | `yes` ,**`no`** , `FG` (foreground) 
| 3G-MIDlet-Auto-Start | Specifies whether to launch the MIDlet when the phone is powered on | `yes` , **`no`** , `FG` (foreground) 
| LGE-MIDlet-autolaunch-after-install | Specifies whether to automatically launch the MIDlet after installation | `yes` , **`no`**
| 3G-MIDlet-After-OTA-Install-Start | Specifies whether to automatically launch the MIDlet after installation | `yes` , **`no`**
| LGE-MIDlet-FlipHandling-Option / 3G-MIDlet-FlipHandling _(For clamshell phones)_| With `No Action` the MIDlet is moved to background on phone close, then restored when opened. With `Pause` the MIDlet is paused while the phone is closed. With `Exit` the MIDlet is closed when closing the phone.  | `No Action` , `Pause` , **`Exit`**
| LGE-MIDlet-flip-pause | On slide-type phones, specifies whether to pause the MIDlet when a "slide-down" event is received. | `yes` , **`no`**
| LGE-MIDlet-Indicator | Specifies whether to show the phone status indicator area. | `SHOW` , `HIDE` , `USINGAPI` (controlled via methods related to FullScreen mode)
| LGE-MIDlet-Exit | Specifies whether the MIDlet will be destroyed or moved to background in a multitasking environment. With `Minimize` the MIDlet will be sent to background and can only be stopped via the applications menu. | `KILL` , **`POPUP`** , `MINIMIZE`
| 3G-MIDlet-Exitkey | Specifies whether the MIDlet will be destroyed or moved to background in a multitasking environment. With `Minimize` the MIDlet will be sent to background and can only be stopped via the applications menu. | `KILL` ,**`POPUP`** , `MINIMIZE`
| LGE-MIDlet-Width / LGE-MIDlet-Height | Specifies the width / height of the MIDlet display. The value should be smaller than the phone's LCD size | `(width/height)`
#### Older devices
| Attribute | Description | Values
| ------------ | ------------ | ------------
| MIDletX-No-Command | Deactivates the command bar when set to true | `true` , `false`
| MIDletX-Big-Icon | Path to the big (32x32) MIDlet icon | `(path)`
| MIDletX-Medium-Icon | Path to the medium (38x18) MIDlet icon | `(path)`
#### Attributes without proper official documentation found:
| Attribute | Description | Known values
| ------------ | ------------ | ------------
|  MIDlet-Touch-Support  | Specifies whether the MIDlet supports touch events. | `true` , `false`
| UseNativeTextButtons | _Unknown_ | `true` , `false`
| ReverseSoftkeys | _Unknown_ | `true` , `false`
| UseNativeCommands | _Unknown_ | `true` , `false`
| LGE-MIDlet-TargetLCD-Height / LGE-MIDlet-TargetLCD-Width | _Unknown_ | `(width/height)`
| LGE-MIDlet-Display-Nav-Keypad | Specifies whether to show a virtual keypad on phones without a physical keypad. | `yes` , `no`
| LGE-MIDlet-On-Screen-Keypad | _Unknown_ (Tried on a real LG phone, did not have any effect. Could be a mixture of Nokia's `Nokia-MIDlet-On-Screen-Keypad`)
| LGE-MIDlet-Display-Mode | _Unknown_ | `both`
| LGE-MIDlet-App-Orientation | Specifies the prefered orientation for the MIDlet cavas | `portrait` , `landscape`
| LGE-MIDlet-Category | Specifies the category where to install the MIDlet | `Applications` , `Games` (known)

### Motorola
| Attribute | Description | Values
| ------------ | ------------ | ------------
| FlipInsensitive | MIDlets with this Motorola specific attribute will enable the MIDlet to run with the flip closed. Audio resources are still available to the MIDlet. | `true` , `false`
| Background | MIDlets with this Motorola specific attribute will continue to run when not in focus. | `true` , `false`
| MOT-MIDlet-Web-Session | APN profile the MIDlet should use. If it does not exists, installation will fail. _MOTOMAGX platform_ | `(profile)`
| Morphing-Mode | Sets the ModeShift technology mode. Valid modes are `MODE_STANDBY` , `MODE_NAVIGATION` , `MODE_PHONE` , `MODE_MUSIC` , `MODE_STILLCAPTURE` , `MODE_VIDEOCAPTURE` , `MODE_STILLPLAYBACK` , `MODE_VIDEOPLAYBACK` | `(mode)`
| Mot-Data-Space-Requirements | Required storage space for the MIDlet data storage in kilobytes. | `(kb)`
| Mot-Program-Space-Requirements | Required storage space for the MIDlet in kilobytes. | `(kb)`
| MIDlet-PreInstalled | Specifies whether the MIDlet was preinstalled on the phone. Does not allows MIDlet removal. | `TRUE` , `FALSE`
| Mot-Midlet-URL | Specifies the JAD URL for the Motorola's Tell-A-Friend feature. | `(url)`
| Motorola-Image-Width / Motorola-Image-Height | Specify the maximum resolution JPEG file (width and height respectively) after opening the phone. | `(pixels)`


#### Motorola iDEN devices
| Attribute | Description | Values
| ------------ | ------------ | ------------
| iDEN-MIDlet-miniJIT | If enabled, miniJIT is used to compile the MIDlet suite code. | `on` , `off`
| iDEN-MIDlet-Name-`(locale)` | Specifies the localized name for the MIDlet suite | `(name)`
| iDEN-Vendor-`(locale)` | Specifies the localized name for the MIDlet vendor | `(name)`
| iDEN-MIDlet-`(locale)`-`(n)` | The name, icon and class of the MIDlet `n` in the MIDlet suite, separated by a comma. | `(name), (icon path), (main class)`
| iDEN-MIDP-KEY-`(key)` | Remaps a specified keycode to a phone key. Can also remap game actions, such that `Canvas.getGameAction(int keycode)` will return the game action when the specified value (in JAD) is passed as a parameter. Valid `(key)` values are: `SELECT` `SOFT-LEFT` `MENU` `SOFT-RIGHT` `LEFT` `RIGHT` `UP` `DOWN` `AUDIO` `VOL-UP` `VOL-DOWN` `OK` `SMART` `PTT` , and valid game actions are `GAME-A` `GAME-B` `GAME-C` `GAME-D` `GAME-UP` `GAME-DOWN` `GAME-LEFT` `GAME-RIGHT` `GAME-FIRE` | `(keycode)`
| iDEN-MIDlet-Phone | Registers the MIDlet as a call receiving application. | `(class)`
| iDEN-MIDlet-Prvtcall | Registers the MIDlet as a call receiving application for dispatching calls | `(class)`
| iDEN-Graphics-Acceleration | Enables hardware graphical acceleration. Mode `auto` uses heusterics to detect the better-performing choice | `on` , `off` , `auto`
#### Notes
- `(locale)` is a two-letters language code. For example, `en` for English, `es` for Spanish, `pt` for Portuguese, and `fr` for French
#### Examples
```
iDEN-MIDlet-Name-es: Serpiente
iDEN-MIDlet-Vendor-es: Motorola
iDEN-MIDlet-es-1: Serpiente, , com.motorola.snake.Snake
```

### Vodafone
| Attribute | Description | Values
| ------------ | ------------ | ------------
| MIDxlet-API | The Vodafone API that should be used. | `VSCL-1.0.1` , `VSCL-1.1.0` , `JSCL-1.2.2` , `JSCL-1.3.2 ` _(known)_
| MIDxlet-Network | Whether network access is required by the MIDlet | `Y` , `N`
| MIDxlet-Resident | Whether to allow running the MIDlet on background | `Y` , `N`
| MIDxlet-Application-Resolution | Resolution of the MIDlet | `(width),(height)`
| MIDxlet-Aux | Whether to allow external video outputs, like AV TV out. | `Y` , `N`
| MIDxlet-MSensor | Whether the MIDlet requires motion sensor capabilities. Non-capable devices throw an error at install. | `Y` , `N`
| MIDxlet-Karaoke | Whether the MIDlet requires launching as a karaoke app. Non-capable devices throw an error at install. | `Y` , `N` , `X`
| MIDxlet-Sound-Priority | Whether the MIDlet requires MP4 (AAC audio) playback features. Non-capable devices throw an error at install. | `Y` , `N`
| MIDxlet-WideScreen | Whether the MIDlet should be drawn in landscape mode. | `Y` , `N`
| MIDxlet-Java-Execution | Whether to allow launching the MIDlet from another MIDlet | `Y` , `N`
| MIDxlet-Execution-Heap | Required heap size in bytes. If not specified, max value is assumed, | `(b)`
| MIDxlet-Bluetooth | Whether the MIDlet requires Bluetooth features. | `Y` , `N`
| MIDxlet-Slave-Application | _Unknown_. Unavailable to untrusted MIDlets | _Unknown_
| MIDxlet-OPGL | Whether the MIDlet uses MEXA OPGL. | `Y` , `N`
| MIDxlet-ExSession | Whether or not to use communication of 1MB or more per session. | `Y` , `N`
| MIDxlet-ExHeap | Whether to use the maximum heap size. | `Y` , `N`
| MIDxlet-Touch | Whether to hide the virtual keyboard on touch devices without physical keypad. | `Y` , `N`
| MIDxlet-Rotate | Whether to change the canvas size on screen rotation, or keep it fixed. | `Y` , `N`

### Research in Motion _(Blackberry)_
| Attribute | Description | Known values
| ------------ | ------------ | ------------
| RIM-COD-Creation-Time | Date/time at which the COD file was created. Example: `1272372497` | `(date)`
| RIM-COD-Module-Dependencies | Comma separated list of modules required by the COD file. Known values: `net_rim_cldc` `net_rim_bbapi_options` `net_rim_bbapi_mailv2` `net_rim_bbapi_invoke` `net_rim_os,net_rim_bb_framework_api` `net_rim_bbapi_browser` `net_rim_bbapi_phone` `net_rim_pdap` | `(module),(module),...`
| RIM-COD-Module-Name | Module provided by this COD file | `(module)`
| RIM-COD-SHA1 | SHA1 hash of the COD file | `(SHA1)` Example: `82 2f 22 b6 e6 34 ef c3 2b 0e a4 96 22 08 c0 60 39 4d db aa`
| RIM-COD-Size | Size in bytes of the COD file | `(size)`
| RIM-COD-URL | URL from which the COD file can be loaded | `(url)`
| RIM-Library-Flags | Reserved for use by RIM | _Unknown_
| RIM-MIDlet-Flags | Reserved for use by RIM. Found to contain numerical values | _Unknown_
| RIM-MIDlet-NameResourceBundle | Name of the resource bundle on which the BlackBerry deviceapplication depends | `(name)`
| RIM-MIDlet-Position | Suggested position on the device's homescreen. Not necessarily honoured. Takes a numerical value | `(n)`

#### Attributes without proper official documentation found:
| Attribute | Description | Known values
| ------------ | ------------ | ------------
| RIM-TouchCompatibilityMode-UserChangeable | _Unknown_ | `true` , `false` (known)
| RIM-TouchCompatibilityMode | _Unknown_ | `true` , `false` (known)
#### Notes
 - For MIDlet suites, appending `-(n)` specifies the parameters for MIDlet `(n)`

### Unknown / Other vendor
| Attribute | Description | Known values
| ------------ | ------------ | ------------
| Navi-Key-Hidden | _Unknown_  | `true` , `false`
| hideUseNativeCommands | _Unknown_ | _Unknown_
| hideUseNativeTextButtons | _Unknown_ | `hide` _(?)_
| ATT-MIDlet-VirtualKeypad-Use | _Unknown_ | `Yes` , `No`

