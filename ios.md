[Back](index.md)

# Holton Monocle iOS

## Technical Documentation

### GETTING STARTED

Holton Monocle iOS requires Xcode 11.0 and above for development. This project uses Swift 5 as the Programming Language, Storyboard for the Interface and CocoaPods for Third Party Libraries. The current Xcode version used for development is 13.2. The minimum iOS Version required is iOS 12.1

### INSTALLATION AND DEVELOPMENT

In order to start with the development, first, you will need an Apple account for development. It must be under the team Rogomi, Inc. Then, open the Monocle.xcworkspace under the repository root directory. If possible, do a pods repo update in order to avoid missing library errors.

### PROGRAMMING LANGUAGE

Holton Monocle iOS uses the latest Swift version, Swift 5, for development.

### MINIMUM VERSION

Holton Monocle iOS requires devices with at least iOS 12.1

### APPLICATION ID

com.holton.monocledemo

### DEBUGGING

We use a few debugging tools to test Holton Monocle's functionalities.

For the Native App, we use Xcode's debugging console to create breakpoints and test variables, API responses, and identify null objects which sometimes causes the crash.

We also use iOS Simulator in order to test the apps in different screen sizes and iOS Versions.

### THIRD-PARTY LIBRARIES


#### Cocoapods
Most of the third party libraries are installed using CocoaPods. They can be added by searching library names found in https://cocoapods.org/, inserting them in the Podfile and running the pod install command in the Terminal.

#### Swift Package Manager (SPM)
Some of the third party libraries are installed using SPM

##### Important Libraries
**Alamofire** - For Web API Communications  
**SwiftyJSON** - To ease up processing of response data  
**ObjectMapper** - To easily create models for response data
**ARCL** - For the AR Camera
**mopub-ios-sdk** - To generate and manage ads for monetization

##### Google and Firebase Platform Libraries.
**Firebase/Analytics** - Used for App Analytics  
**Firebase/Crashlytics** - Used to identify causes of crashes from users  
**Firebase/Performance** - Used to monitor application performance
**Firebase/Auth** - Used to handle the user Authentication
**Firebase/Firestore** - Used to handle data stored from Firestore which is used as the main database of the app
**FirebaseFirestoreSwift** - Used to integrate Firestore smoothly on swift
**GoogleSignIn** - Used to sing in by Google
**GoogleMaps** - Used to show the Google Map
**GooglePlaces** - Used to show the places on the Google Map



##### UI Libraries
**IQKeyboardManagerSwift** - To automatically scroll up the UITextView on screen when the keyboard is up.  
**IBAnimatable** - To easily add special UI Designs on specific views, and see them reflected on the Interface Builder. Also has methods to animate views.  
**MBProgressHUD** - Used to add heads up display on screen to indicate loading while user is waiting for data to be loaded from the API  
**SkeletonView** - Used to add special UI designs to indicate loading
**Pulley** - Used to create and manage the drawer views


##### Other Useful Libraries 
**ReachabilitySwift** - Used to check internet connection status   


### ACTIVITIES AND CONTROLLERS  

#### Core Classes
- **AppDelegate** - manages most of the pre-startup items like Firebase configurations, etc.
  ##### Configured items
  - Firebase Configuration - Analytics and crashlytics.
  - Google Sign In - Sets the API key for Google Sign In
  - IQKeyboardManager - enables the global usage of IQKeyboardManager.
  - Firebase Firestore - enables the app to use Firestore.  
  - Mo Pub - enables the app to use Mo Pub for ads.  


#### View Controllers

- **LandingViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `viewDidAppear(_ animated: Bool)`
  - `proceed()`
  - `proceedToAuth()`
  - `proceedToApp()`
  - `checkIfLoggedIn()`
  - `unwindFromSignIn(unwindSegue: UIStoryboardSegue)`
  - `unwindFromLogout(unwindSegue: UIStoryboardSegue)`
  - `rotate()`

- **SignInViewController** - manages the user Authentication via Firebase, Google, or Apple.    
  ##### Methods
  - `viewDidLoad()`
  - `passwordEyeButtonUp(_ sender: Any)`
  - `refreshEyecons()`
  - `didTapGoogleSignIn(_ sender: Any)`
  - `didTapAppleSignIn(_ sender: Any)`
  - `unwindToSignIn(unwindSegue: UIStoryboardSegue)`
  - `didTapSignIn(_ sender: Any)`
  - `successfullySignedIn()`
  - `signIn()`
  - `googleSignIn()`
  - `validateInputs()`

- **SignUpViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `passwordEyeButtonUp(_ sender: Any)`
  - `confirmPasswordEyeButtonUp(_ sender: Any)`
  - `refreshEyecons()`
  - `didTapRegister(_ sender: Any)`
  - `didTapGoogleSignIn(_ sender: Any)`
  - `didTapAppleSignIn(_ sender: Any)`
  - `didTapForgotPassword(_ sender: Any)`
  - `signUp()`
  - `successSignUp()`
  - `googleSignIn()`


