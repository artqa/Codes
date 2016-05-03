adb
adb devices
adb logcat -d> ~/Desktop/logs.txt  -- MAC
adb logcat - d> %UserProfile%\Desktop\logs.txt -- Win
adb shell screencap -p | perl -pe 's/\x0D\x0A/\x0A/g' > screenshot.png   -- MAC
******************Win screenshot*****************
adb shell screencap –p /sdcard/screenshot.png
adb pull /sdcard/screenshot.png "%UserProfile%\Desktop\screenshot.png"
adb shell rm /sdcard/screenshot.png
***********************************************************************
Windows
adb shell screenrecord --size 360x640 --bit-rate 2000000 --time-limit 30 /sdcard/ellowoyld.mp4
adb pull /sdcard/ellowoyld.mp4 "%UserProfile%\Desktop\ellowoyld.mp4"
adb shell rm /sdcard/ellowoyld.mp4

Mac
adb shell screenrecord --size 360x640 --bit-rate 2000000 --time-limit 30 /sdcard/ellowoyld.mp4
adb pull /sdcard/ellowoyld.mp4 ~/Desktop/$ellowoyld.mp4
adb shell rm /sdcard/ellowoyld.mp4

--size: Set the WIDTHxHEIGHT of the video. It has to be a supported size. The default is our device’s main resolution or 720p if that doesn’t work. Personally I find 360x640 to be perfect for bugs. We really don’t need to go much higher. Also, note that the above script records in Portrait mode. If we want to record in Landscape mode instead we just switch the numbers round, for example, 640x360.

--bit-rate: Set the video bit rate. The default is 4Mbps. Be careful here, the documentation is wrong! It’s in bps NOT Mbps. So if you want to manually set the bit-rate to the default you would enter "4000000". I find 2Mbps acceptable at 360x640 resolution. 1Mbps is still better quality than most of the screencasts I’ve seen in bug reports.

--time-limit: The length of video to record in seconds. The default, and maximum, is 3 minutes. So the above script will record 30 seconds of video.

https://www.utest.com/courses/android-debug-bridge-part-4-install-apk-files-and-connect-over-wifi
