----------------------stackoverflow/android-stop-emulator-from-command-line


Use adb kill-server. It should helps. or

adb -s emulator-5554 emu kill, where emulator-5554 is the emulator name.

For Ubuntu users I found a good command to stop all running emulators (Thanks to @uwe)

adb devices | grep emulator | cut -f1 | while read line; do adb -s $line emu kill; done

---------------------interpreting this as a package uri, dart:ui missing
https://github.com/dart-lang/sdk/issues/35279

I got this error from android studio and running my client as normal. (i thought).
It turned out I somehow had selected another run-target for main.dart.
Guessing pure dart code (dart icon, not flutter).
Switched to main.dart with Flutter icon and now it runs again.

----------------------stackoverflow/error-while-waiting-for-device-time-out-after-300seconds-waiting-for-emulator-t
You might have forwarding enabled on adb. You can try this: Quit Android studio and launch terminal. Run these commands:

adb kill-server
adb forward --remove-all
adb start-server

and killing adb.exe process tree doesn't help for stackoverflow/android-emulator-5554-offline
instead the coldboot (or uncheck launch from snapshot in eclipse) worked well.