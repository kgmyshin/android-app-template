# Android App Template

まず初めに必ず ① `app/build.gradle` と ② `app/src/main/AndroidManifest.xml` にある `com.kgmyshin.sample` を適切なパッケージ名に変更してください。

① app/build.gradle

```
  defaultConfig {
    applicationId "com.kgmyshin.sample" // ← 修正
    ...
  }
```

② app/src/main/AndroidManifest.xml

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  package="com.kgmyshin.sample"> //  ← 修正
```
