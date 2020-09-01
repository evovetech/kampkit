# Troubleshooting

**Q:** When I tried to build the library, why did I get the following error? "SDK location not found. Define location with an ANDROID_SDK_ROOT environment variable or by setting up the sdk.dir path in your project's local properties file... "

**A:** This error occurs when the project does not know the location of your local Android SDK. It should be located at `/Users/[YOUR_USER_NAME]/Library/Android/sdk`, which is where Android Studio recommends you put it during initial setup/installation.

Opening this project in Android Studio will automatically create and configure a `local.properties` file for you. If you want to do that yourself, create a file called `local.properties` in the root directory of this project. Paste in the following line, replacing [YOUR_USER_NAME] with, you guessed it, the username you're using on your local machine:

```
sdk.dir=/Users/[YOUR_USER_NAME]/Library/Android/sdk
```

>**Note**: The `local.properties` file should not be committed to version control, as the path will be different for anyone >else working on the project.


**Q:** When I tried to run the project in Xcode, why did I get the following error? "Framework not found shared_umbrella".

**A:** You probably opened the `.xcodeproj` file instead of the `.xcworkspace`. Close out the `.xcodeproj` and open the `.xcworkspace` and run again.

 To learn more about Cocoapods and how to use them, check out [their official guide](https://guides.cocoapods.org/using/index.html).


**Q:** The Xcode project won't compile. On the `import shared` line in Swift, I'm getting a compilation error "no
 such module: 'shared'".

**A:** Try closing Xcode and deleting the `Pods/` folder located in the root directory of the iOS project. Then run the command `pod install` in that same iOS root directory (which is `/KaMPStarter/ios/` to be specific). This command will generate a new `Pods` folder. Reopen the `.xcworkspace` file and try to build again.

> Note: We're still not quite sure as to the cause of this error. Possible factors include differing versions of Cocoapods or >Xcode.

**Q:** I've just opened the android studio project, but I can't run anything and I'm getting this error: `LocationAwareException: New Gradle Sync is not supported due to containing Kotlin modules`. 

**A:** This can happen when you choose to `open an existing Android Studio project`. The project may have existing configurations that's confusing Android Studio. Close the Android Studio window, and in the Welcome to Android Studio window choose the `Import Project` option on the right. Importing the project this way should point Android Studio in the right direction and import correctly. If this doesn't work, try deleting the .idea folder from the root directory and try `Import Project` again.

## More to Come!

[Let us know](../CONTACT_US.md) what issues you run into
