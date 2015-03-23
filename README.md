### JXcore / Node.JS for Android sample

This project is a kind of 'hello world' for JXcore's native interface on an Android application. 
It's an Eclipse IDE project. You also need Android-NDK is installed on your system.

The sample project use JXcore SpiderMonkey JIT build for Android ARM and Intel processors.  
Prebuilt JXcore binaries are already available under 'jxcore-droid/jxcore-binaries'

### Before Start
[How to setup Android NDK for Eclipse IDE](http://tools.android.com/recent/usingthendkplugin)  
[Download Android NDK](https://developer.android.com/tools/sdk/ndk/index.html)  
[Eclipse Android Plugin](http://developer.android.com/tools/sdk/eclipse-adt.html)

### Tips for Eclipse
Open Eclipse IDE and from the 'Project Explorer', Right Click->New->Other  
Android->Android Project from Existing Code  
Pick 'jxcore-droid' folder and move forward.

Do exactly the same with 'android-support-v7....' folder.

After all, you should have two eclipse projects on 'Project Explorer'. 
One of them is an Android support project. The other one is JXcore sample
project. Make sure you have both of them on Eclipse. 

Right click to 'jxcore-droid' project -> Android Tools -> Add Support Library .. and follow the steps.

If you have errors etc. (from top menu) Project -> Clean -> (Select both of the projects)

Right click to 'android-support-v7...' project and 'Build'. 

You may need to update some project settings for your environment. Feel free to ask from Github!

### Tips for Intellij 14/Android Studio
1. File->Import Project and import jxcore-android-basics/jxcore-droid/.project
2. Press Next 2 times
3. Select Android API 21 and press Finish
4. Select new window
5. You will get an error "Unknown modules detected android-support-v7-appcompat", just hit OK
6. You will see "Unknown Natures Detected", ignore that, you will see "Import Android Dependencies from Property Files", hit ok
7. Go to File->Project Structure, then Project Settings/Modules/jxcore-droid and delete com.android.ide.eclipse.adt.DEPENDENCIES and android-support-v7-appcompat
8. While still inside of File->Project Structure go to Project Settings/Modules/appcompat_v7, hit the green plus and choose Jars or directories. Then navigate down to C:\Program Files (x86)\Android\android-studio\sdk\extras\android\support\v7\appcompat\libs\android-support-v4.jar (or where ever your android SDK is) and hit OK. 
9. Make sure to check 'Export' when the android-support-v4.jar entry is added to the module list. Then hit OK.
9. On the command line go to jxcore-android-basics/jxcore-droid and run [path to Android NDK]/ndk-build
10. Go back to the project and run Build->Make. It will fail the first time complaining about package R does not exist. Try it again. Now it should build fine.

For those on Windows there have been some issues getting the Android NDK to run correctly with this project. One work around is to run a Linux VM with the Android NDK and put the Git Depo into a folder that is shared both with the Windows host and with the Linux VM. One can then run ndk-build in Linux but do all other development and launch to Android devices with Intellij in Windows.
