# cordova-plugin-background-app-run

Cordova plugin to run app in background with foreground services, WorkManager, and Picture-in-Picture support.

## Installation

```bash
cordova plugin add cordova-plugin-background-app-run
```

**Note:** If you encounter a "module already defined" error after installation, try:
1. Remove and re-add the plugin:
   ```bash
   cordova plugin remove cordova-plugin-background-app-run
   cordova plugin add cordova-plugin-background-app-run
   ```
2. Clean and rebuild your project:
   ```bash
   cordova clean
   cordova build android
   ```

## Usage

### Start Background Service

Start the background service with Picture-in-Picture support:

```javascript
cordova.plugins.backgroundAppRun.startServ(
  function(success) {
    console.log('Background service started:', success);
  },
  function(error) {
    console.error('Error starting service:', error);
  }
);
```

### Stop Background Service

Stop the background service:

```javascript
cordova.plugins.backgroundAppRun.stopServ(
  function(success) {
    console.log('Background service stopped:', success);
  },
  function(error) {
    console.error('Error stopping service:', error);
  }
);
```

### Start Sound Service

Start the background sound service:

```javascript
cordova.plugins.backgroundAppRun.startSoundServ(
  function(success) {
    console.log('Sound service started:', success);
  },
  function(error) {
    console.error('Error starting sound service:', error);
  }
);
```

### Stop Sound Service

Stop the background sound service:

```javascript
cordova.plugins.backgroundAppRun.stopSoundServ(
  function(success) {
    console.log('Sound service stopped:', success);
  },
  function(error) {
    console.error('Error stopping sound service:', error);
  }
);
```

### Fire Event

Fire a custom event:

```javascript
cordova.plugins.backgroundAppRun.fireEvent(
  'eventData',
  function(success) {
    console.log('Event fired:', success);
  },
  function(error) {
    console.error('Error firing event:', error);
  }
);
```

### Background Delete File

Schedule a file deletion in the background using WorkManager:

```javascript
cordova.plugins.backgroundAppRun.backgroundDeleteFile(
  'file:///path/to/file',
  function(success) {
    console.log('File deletion scheduled:', success);
  },
  function(error) {
    console.error('Error scheduling deletion:', error);
  }
);
```

## Important Note

If you encounter an error with this import line:

```java
import com.berger.app.cbservice.R;
```

You must manually set the package name of your application. For example:

- For fusion app: `import com.berger.retail.master.R;`

The `R` class is used to access audio files and other resources in your application. Update the import statement in `src/android/makeSoundService/makeSoundService.java` to match your application's package name.

