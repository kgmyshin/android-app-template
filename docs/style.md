---
title: Style Guide
layout: default
---

# Style Guide

## 原則
原則として、[Android Style Guide](https://developer.android.com/kotlin/style-guide)に従います。
Android Style Guideに言及されていない項目については[Kotlin Coding Conventions](https://kotlinlang.org/docs/reference/coding-conventions.html)に従います。

## 独自のもの

### Indent
`indent` 及び `continuation indent` は **2** とする。

## 返り値の型の記述を省略してはいけない

次のように、返り値の記述を省略するのはやめましょう。

```
  // × bad
  fun getPosition() = {数字を返す処理}

  // ○ ok
  fun getPosition(): Int = {数字を返す処理}
```

理由はとしては、例えば、本来数字を返す処理のところを間違って文字列を返してしまった場合に、省略しない形で書いていれば必ずコンパイルエラーになりますが、
省略してしまうとコンパイルエラーにならずに発覚が遅れてしまうケースがあるからです。

```
  // × コンパイルエラーにならない
  fun getPosition() = {本当は数字を返す処理を書きたいが文字列を返した}

  // ○ コンパイルエラーになる
  fun getPosition(): Int = {本当は数字を返す処理を書きたいが文字列を返した}
```
