## AppRating - iOS App Rating for Swift 3

AppRating is a simple yet powerful App Review Manager for iOS and OSX written in Swift. It is based on [Armchair](https://raw.githubusercontent.com/UrbanApps/Armchair/) but mainly rewritten for Swift3.

## What's new?

- SKStoreReviewController - Now supporting the brand new iOS 10.3 API SKStoreReviewController which makes it really easy to get a huge number of ratings for your app. It opens the rating directly in an alert:
- **IMPORTANT** : SKStoreReviewController is only available for Xcode 8.3+, if you want to test, please checkout the iOS_10.3 branch (see cocoapods installation guide below).

![AppRating supports the brand new SKStoreReviewController API](https://pbs.twimg.com/media/C3BFBGMWEAAL5Di.png)

## Why AppRating?

The average end-user will only write a review if something is wrong with your App. This leads to an unfairly negative skew in the ratings, when the majority of satisfied customers don’t leave reviews and only the dissatisfied ones do. In order to counter-balance the negatives, AppRating prompts the user to write a review, but only after the developer knows they are satisfied. For example, you may only show the popup if the user has been using it for more than a week, and has done at least 5 significant events (the core functionality of your App). The rules are fully customizable for your App and easy to setup.

## Requirements

- Xcode 8.3+ (get the beta version at [Apple Developer](https://developer.apple.com/))
- iOS 9.0+

## Installation

### CocoaPods

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

> CocoaPods 0.39.0+ is required to build AppRating.

To integrate AppRating into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'
use_frameworks!

pod 'AppRating', '>= 0.0.1'
```

Then, run the following command:

```bash
$ pod install
```

If you want to test SKStoreReviewController, use the iOS_10.3 branch:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'
use_frameworks!

pod 'AppRating', git: 'https://github.com/grizzly/AppRating.git', branch: 'iOS_10.3'
```


## Usage

### Simple 1-line Setup

AppRating includes sensible defaults as well as reads data from your localized, or unlocalized `info.plist` to set itself up. While everything is configurable, the only **required** item to configure is your App Store ID. This call should be made as part of your App Delegate's `initialize()` function

```swift
AppRating.appID("12345678")
```

That's it to get started. Setting AppRating up with this line uses some sensible default criterion (detailed below) and will present a rating prompt whenever they are met.


## What's Planned?

There are some ideas we have for future versions of AppRating. Feel free to fork/implement if you would like to expedite the process.

- Get 100% Unit Test coverage
- Add additional localizations: ongoing
- [Your idea](https://github.com/grizzly/AppRating/issues)

## Bugs / Pull Requests
Let us know if you see ways to improve AppRating or see something wrong with it. We are happy to pull in pull requests that have clean code, and have features that are useful for most people. While the Swift community is still deciding on proper code structure and style, please refrain from simple style complaints (space > tabs, etc...)

## License

AppRating is released under an MIT license. See [LICENSE](https://github.com/grizzly/AppRating/blob/master/LICENSE) for more information
