# Android App Template

## SetUp

### パッケージ名の変更

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

### Firebase App Distribution のセットアップ

次の手順で、`FIREBASE_TOKEN`を取得して、ローカルマシンの環境変数に設定しましょう。

 1. [Firebaseプロジェクトをセットアップ](https://firebase.google.com/docs/android/setup?hl=ja#console)
 2. `app/google-services.json`を上書きする
 3.  [プラグインのログイン操作で Google アカウントにログインする](https://firebase.google.com/docs/app-distribution/android/distribute-gradle?hl=ja#google-acc-gradle) を見て、`FIREBASE_TOKEN`を取得する
 4. `FIREBASE_TOKEN`を環境変数に設定する

### Circle CIのセットアップ

`Firebase App Distribution のセットアップ` で取得した `FIREBASE_TOKEN` を circleci の環境変数に設定しましょう。
