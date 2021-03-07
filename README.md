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

それぞれ次の環境変数をcircleciに設定しましょう。

| 環境変数名 | 説明 | 取得方法 |
| --- | --- | --- |
| FIREBASE_TOKEN | Firebase App Distributionで使用するToken |  `Firebase App Distribution のセットアップ`で取得した FIREBASE_TOKEN です |
| DANGER_GITHUB_API_TOKEN | DangerがPull-Requestにコメントするために必要なTOken | [SETTING UP AN ACCESS TOKEN](https://danger.systems/guides/getting_started.html#setting-up-an-access-token) |

### Github Pages のセットアップ

* Settings -> Github Pages で Branch を `main` にして ディレクトリを `root` を選べば、ドキュメントが公開されます。
