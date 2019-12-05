# TransitionableTab


[![Version](https://img.shields.io/cocoapods/v/Hero.svg?style=flat)](http://cocoapods.org/pods/Hero)
![Xcode 9.0+](https://img.shields.io/badge/Xcode-9.0%2B-blue.svg)
![iOS 8.0+](https://img.shields.io/badge/iOS-8.0%2B-blue.svg)
![Swift 4.0+](https://img.shields.io/badge/Swift-4.0%2B-orange.svg)
[![License](https://img.shields.io/cocoapods/l/Hero.svg?style=flat)](https://github.com/lkzhao/Hero/blob/master/LICENSE?raw=true)

**TransitionableTab** makes it easy to animate when switching between tab .

## Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Communication](#communication)
- [Credits](#credits)
- [License](#license)

## Requirements

- iOS 8.0+
- Xcode 9.0+
- Swift 4.0+

## Installation

### Swift Package Manager:

Add the following line to your `Package.swift`:

```swift
dependencies: [
    // ...
    .package(url: "https://github.com/Wistas23/TransitionableTab.git"),
],
```

---


## Usage

The usage of **TransitionableTab** is very simple

```swift
import TransitionableTab

class TabBarController: UITabBarController {

    override func viewDidLoad() {
        super.viewDidLoad()
        self.delegate = self
    }
}

extension TabBarController: TransitionableTab {

    func tabBarController(_ tabBarController: UITabBarController, shouldSelect viewController: UIViewController) -> Bool {
        return animateTransition(tabBarController, shouldSelect: viewController)
    }
}
```

### Custom

```swift
public protocol TransitionableTab: UITabBarControllerDelegate {

    func transitionTimingFunction() -> CAMediaTimingFunction

    func transitionDuration() -> CFTimeInterval

    func fromTransitionAnimation(layer: CALayer, direction: Direction) -> CAAnimation

    func toTransitionAnimation(layer: CALayer, direction: Direction) -> CAAnimation
}
```

If you want to know more detailed usage, please refer to Example.

## Communication

- If you **found a bug**, open an issue.
- If you **have a feature request**, open an issue.
- If you **want to contribute**, submit a pull request.

## Credits

- GwangBeom Park ([@gwangbeom](https://github.com/ParkGwangBeom))

## License

TransitionableTab is released under the MIT license. See LICENSE for details.

