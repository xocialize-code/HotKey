# HotKey

[![Version](https://img.shields.io/github/release/xocialize-code/HotKey.svg)](https://github.com/xocialize-code/HotKey/releases)
![Swift Version](https://img.shields.io/badge/swift-5.0.1-orange.svg)

Simple global shortcuts in macOS. HotKey wraps the Carbon APIs for dealing with global hot keys to make it easy to use in Swift.

**HotKey, along with [Color](https://github.com/soffes/Color), were created for use in [Contrast](https://usecontrast.com), a macOS app for checking designs for accessible color combinations.**

## Installation

### Swift Package Manager

For installation with [Swift Package Manager](https://github.com/apple/swift-package-manager), simply add the following to your `Package.swift`:

``` swift
.package(url: "https://github.com/soffes/HotKey", from: "0.1.4")
```

## Usage

Simply initialize a `HotKey` with a key and modifiers:

```swift
// Setup hot key for ⌥⌘R
let hotKey = HotKey(key: .r, modifiers: [.command, .option])
```

This is a convenice initializer that creates a `KeyCombo` for you. You can also initialize with a Carbon key code and Carbon modifier flags if you’re feeling old school.

Now you can set the `keyDownHandler` and get callbacks for when your hot key is pressed:

```swift
hotKey.keyDownHandler = {
  print("Pressed at \(Date())")
}
```

You can also implement `hotKey.keyUpHandler` if you’d like.

You don’t need to think about when handlers are registered and unregistered. This all happens automatically based on the `HotKey` object’s lifecycle.


## Thanks

HotKey credit goes to Soffes/HotKey.  Minor updates to keep it compiling for this repo.
