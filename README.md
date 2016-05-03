adb
adb devices
adb logcat -d> ~/Desktop/logs.txt  -- MAC
adb logcat - d> %UserProfile%\Desktop\logs.txt -- Win
adb shell screencap -p | perl -pe 's/\x0D\x0A/\x0A/g' > screenshot.png   -- MAC

