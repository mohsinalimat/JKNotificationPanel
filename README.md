# JKNotificationPanel


[![Version](https://img.shields.io/cocoapods/v/JKNotificationPanel.svg?style=flat)](http://cocoapods.org/pods/JKNotificationPanel)
[![License](https://img.shields.io/cocoapods/l/JKNotificationPanel.svg?style=flat)](http://cocoapods.org/pods/JKNotificationPanel)
[![Platform](https://img.shields.io/cocoapods/p/JKNotificationPanel.svg?style=flat)](http://cocoapods.org/pods/JKNotificationPanel)

Simple, Customizable notification panel

![JKNotificationPanel](https://raw.githubusercontent.com/macfeteria/JKNotificationPanel/master/Screenshot/jknotification_screen.gif)

## Requirements

- Swift 2.1
- Xcode 6
- iOS 8.0 or above

## Installation

JKNotificationPanel is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "JKNotificationPanel"
```

## Usage
Using JKNotification panel is very easy.

### Basic Usage

First of all you need to create JKNotifictionPanel
```Swift
let panel = JKNotificationPanel()
```
### Displaying the basic panel
```Swift
panel.showNotify(withStatus: .SUCCESS, inView: self.view, message: "Success to upload all images.")
```
### Displaying the panel below the navigation
```Swift
panel.showNotify(withStatus: .FAILED, belowNavigation: self.navigationController!)
```
### Custom View
```Swift
let nib = UINib(nibName: "CustomNotificationView", bundle: NSBundle(forClass: self.dynamicType))

let customView  = nib.instantiateWithOwner(nil, options: nil).first as! UIView
let width:CGFloat = UIScreen.mainScreen().bounds.size.width
customView.frame = CGRectMake(0, 0, width, 20)

panel.showNotify(withView: customView, belowNavigation: self.navigationController!)
```

### Tab to dissmiss
```Swift
panel.timeUntilDismiss = 0 // zero for wait forever
panel.enableTabDismiss = true
panel.showNotify(withStatus: .SUCCESS, belowNavigation: self.navigationController!, message: "Tap me to dissmiss")

```


### Delegate
```Swift
func notificationPanelDidDismiss ()
func notificationPanelDidTab()
```

### User tab action
If you don't want to use delegate you can also use tab action instead. 
```Swift
panel.timeUntilDismiss = 0 // zero for wait forever
panel.enableTabDismiss = false
panel.addPanelDidTabAction() {
self.notificationPanelDidTab()
}
panel.showNotify(withStatus: .SUCCESS, belowNavigation: self.navigationController!, message: "Tab me to show alert")
```

## Author

Ter,
http://www.macfeteria.com

## License

JKNotificationPanel is available under the MIT license. See the LICENSE file for more info.
