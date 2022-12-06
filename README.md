# React-Native-Build-Error

https://github.com/OmarThinks/ReactNativeBuildError

# Acknowledgement:

Thank you so much React Native Team for your hard and consistent work.

# Reporducability of issue:

Here the are 2 projects: https://github.com/OmarThinks/ReactNativeBuildError  
I have created a Github repo to make it easy for you to spot the error.  
JS and TS projects.  
I have been stuck here for 3 consecutive days.  
I tried everything I could find.  
https://stackoverflow.com/questions/59695135/react-native-android-build-process-command-npx-cmd-finished-with-non-zero
https://github.com/facebook/react-native/issues/28510  
None of these soltions worked.

# How I Generated these projects:

```bash
npx react-native init AwesomeProject
```

```bash
npx react-native init AwesomeTSProject --template react-native-template-typescript
```

I did not add any other code to the templates, just signning the keys.

# Error:

```bash
$ ./gradlew bundleRelease
> Task :app:bundleReleaseJsAndAssets FAILED

FAILURE: Build completed with 2 failures.

1: Task failed with an exception.
-----------
* What went wrong:
Execution failed for task ':app:bundleReleaseJsAndAssets'.
> Process 'command 'cmd'' finished with non-zero exit value 1

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
==============================================================================

2: Task failed with an exception.
-----------
* What went wrong:
java.lang.StackOverflowError (no error message)

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
==============================================================================

* Get more help at https://help.gradle.org

Deprecated Gradle features were used in this build, making it incompatible with Gradle 8.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

See https://docs.gradle.org/7.5.1/userguide/command_line_interface.html#sec:command_line_warnings

BUILD FAILED in 4s
8 actionable tasks: 3 executed, 5 up-to-date
```

# Key:

Key is already generated on `/android/app/my-upload-key.keystore`. But, if you want to regenerate a new key, you can follow the steps below:

```bash
keytool -genkey -v -keystore my-upload-key.keystore -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000


MYAPP_UPLOAD_STORE_FILE=my-upload-key.keystore
MYAPP_UPLOAD_KEY_ALIAS=my-key-alias
MYAPP_UPLOAD_STORE_PASSWORD=abcdefghijklmnop
MYAPP_UPLOAD_KEY_PASSWORD=abcdefghijklmnop
```

# Acknowledgement (Again):

Thank you so much React Native Team for your hard and consistent work.  
You saved us from Java.
