# APPropriate
![Setting up APPropriate](https://lh3.googleusercontent.com/UsSgX92lc14WNca0jeF9ygaQH-9A4E1RD2JZ2MeR4WYAgK20YuwYG4DxNKUfEIcmYV0=w206 "Setting up APPropriate") ![Synchronising data](https://lh3.googleusercontent.com/axuLBrG7gTaV3rLtcAp58Yl6yFf0JLuK-O6Yb96v5R_Jx77u8WxaZtwbAvjwMhWpzGk=w206 "Synchronising data") ![Viewing data](https://lh3.googleusercontent.com/GU8tksiUDfNZ-1f6NxYti4_mLXxXC7QxONvbXLxa5UvHUO7Xye8DtzzssOsa1QeB2Ws=w206 "Viewing data") ![APPropriate settings](https://lh3.googleusercontent.com/oAL8FKqvWRZlFyOFYbFxvPqC4UxstoWb7fKoryClkYzncUUOKMVDOxE0OiG8QsYKnKdR=w206 "APPropriate settings")

APPropriate separates your phone's important content from the phone itself, letting you view or edit your data anywhere, on any Android device, with no internet connection required. Using APPropriate and its accompanying hardware module, a borrowed phone temporarily becomes your own, showing your own photos, contacts and messages.

[Download the app](https://play.google.com/store/apps/details?id=ac.robinson.pod) to use with an existing APPropriate hardware module, or follow the instructions below to get started with your own device.

See the [toolkit website](http://digitalinclusiontoolkit.org/) and [research project website](http://www.reshapingthefuture.org/) for more details and related work.

## Setting up your own APPropriate hardware
APPropriate is designed to be deeply integrated into mobile device hardware and software platforms, allowing its users to truly appropriate any available device. For now, we have created a hardware demonstration of its capabilities by adopting a wireless USB stick (a [Verbatim MediaShare Wireless Mini](https://www.verbatim.com.hk/mediashare-wireless-mini.html)).

The following steps assume that you own one of these devices (and that it has an accompanying SD card), and that you have built your own version of the APPropriate Android app using the code in this repository:

1. Turn on your MediaShare Wireless Mini (from this point onwards, referred to as *APPropriate*) using the power switch on its side. The device's blue WiFi status indicator light should first turn solid, and then begin to blink. Wait for the status indicator light to stop blinking before continuing to the next step.

2. Reset any existing settings your APPropriate may have (note: if you have a new, unused APPropriate, you may skip this step and go to step 3):

    2.1. Remove the SD card from your APPropriate in order to ensure any existing data is not at risk.

    2.2. Reset your APPropriate to its factory state by pressing a pin or straightened paper clip into the small reset button hole to the right of the power switch. Hold down this reset button for about 10 seconds. When you release the reset button, the APPropriate's status light should remain on for a few seconds, and then begin blinking, indicating that the device is restarting. Wait for the light to stop blinking before continuing.

    2.4. Re-insert the SD card into your APPropriate. If the device's status indicator light begins flashing, wait for this to turn solid before continuing.

3. Connect to the `Verbatim-XXXX` WiFi network, which should now be visible (where `XXXX` represents the four characters printed on the back of your APPropriate). The default password is `verbatim`.

4. Visit http://10.10.10.254 in a web browser, and log in as `admin`, leaving the password field blank. Click on `Settings`.

5. Update the APPropriate's configuration, setting the following options:

    5.1. User Manager > Admin: Set the password to the same value you have chosen for `project.ext.adminPassword` in [config.gradle](app/config.gradle).
    
    5.2. Services Settings > Samba Service: Disable this service (note: the selected value is the one highlighted in blue)
    
    5.3. Services Settings > Media Service: Disable this service (note: the selected value is the one highlighted in blue)
    
    5.2. System Settings > Time Settings: Turn off `Automatically synchronize with an Internet Time Server` (note: the selected value is the one highlighted in blue). Set the date and time to the correct current values.
    
    5.4. Network Settings > Wi-Fi & LAN: Set SSID to `Pod-5feceb66ffc86f38`, security to `WPA2-PSK` and password to the same one you have chosen for `project.ext.networkPassword` in [config.gradle](app/config.gradle).

6. Save your changes to the APPropriate's configuration, and then wait for the device to restart itself (see status indicator light stages in step 1).

7. Open the APPropriate Android app, and enter the PIN `0000` to connect to your newly set up device. You can now proceed through the synchronisation instructions in the app, and change your PIN to a more secure and private one.

## License
Apache 2.0
