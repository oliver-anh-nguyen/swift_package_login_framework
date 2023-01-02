# swift_package_login_framework

## Usage example

1. Import the LoginFramework in your AppDelegate
```swift
import LoginFramework
```
2. In didFinishLaunchingWithOptions in your AppDelegate
- To show default Layout Signin
```swift
import UIKit
import LoginFramework
@main
class AppDelegate: UIResponder, UIApplicationDelegate {
    var window: UIWindow?
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        self.window = UIWindow(frame: UIScreen.main.bounds)
        let signinViewController = SigninViewController()
        window?.rootViewController = signinViewController
        window?.makeKeyAndVisible()
        return true
    }
}
```
- To customize layout, we have two types of layout configuration: SimpleLayout & AdvancedLayout
```swift
let simpleLayout = SimpleLayout()
simpleLayout.primaryColor = UIColor(red: 56/255.0, green: 112/255.0, blue: 58/255.0, alpha: 1.0)
simpleLayout.backgroundColor = .red
simpleLayout.logoImage = UIImage(named: "logo.png")
simpleLayout.backgroundImage = UIImage(named: "background.png")
let signinViewController = SigninViewController()
signinViewController.layout = .Simple(layout: simpleLayout)
```
```swift
let advancedLayout = AdvancedLayout()
advancedLayout.linePassword.color = .green
advancedLayout.lineUsername.color = .green
advancedLayout.tfUsername.textColor = .blue
advancedLayout.tfPassword.textColor = .blue
advancedLayout.buttonForgot.fontColor = .blue
advancedLayout.imgLogo.image = UIImage(named: "logo.png")
advancedLayout.textSignin.font = UIFont.systemFont(ofSize: 17)
let signinViewController = SigninViewController()
signinViewController.layout = .Advanced(layout: advancedLayout)
