# cordova-plugin-background-app-run

Cordova plugin to run app in background with foreground services, WorkManager, and Picture-in-Picture support.

## Installation

```bash
cordova plugin add cordova-plugin-background-app-run
```

## Important Note

If you encounter an error with this import line:

```java
import com.berger.app.cbservice.R;
```

You must manually set the package name of your application. For example:

- For fusion app: `import com.berger.retail.master.R;`

The `R` class is used to access audio files and other resources in your application. Update the import statement in `src/android/makeSoundService/makeSoundService.java` to match your application's package name.

