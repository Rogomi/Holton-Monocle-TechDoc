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

- **ResetPasswordViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapBackButton(_ sender: Any)`
  - `didTapSend(_ sender: Any)`
  - `goNext()`
  - `sendResetEmail()`

- **ResetEmailViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapOpenEmail(_ sender: Any)`

- **AppleAuthViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `presentationAnchor(for controller: ASAuthorizationController)`
  - `handleAuthorizationAppleIDButtonPress()`
  - `randomNonceString(length: Int = 32)`
  - `startSignInWithAppleFlow()`
  - `sha256(_ input: String)`
  - `authorizationController(controller: ASAuthorizationController, didCompleteWithAuthorization authorization: ASAuthorization)`
  - `authorizationController(controller: ASAuthorizationController, didCompleteWithError error: Error)`
  - `appleSignIn()`

- **ARCameraViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapCloseButton(_ sender: Any)`
  - `viewDidLayoutSubviews()`
  - `touchesBegan(_ touches: Set<UITouch>, with event: UIEvent?)`
  - `didReceiveMemoryWarning()`
  - `sceneLocationViewDidAddSceneLocationEstimate(sceneLocationView: SceneLocationView, position: SCNVector3, location: CLLocation)`
  - `sceneLocationViewDidRemoveSceneLocationEstimate(sceneLocationView: SceneLocationView, position: SCNVector3, location: CLLocation)`
  - `sceneLocationViewDidConfirmLocationOfNode(sceneLocationView: SceneLocationView, node: LocationNode)`
  - `sceneLocationViewDidSetupSceneNode(sceneLocationView: SceneLocationView, sceneNode: SCNNode)`
  - `sceneLocationViewDidUpdateLocationAndScaleOfLocationNode(sceneLocationView: SceneLocationView, locationNode: LocationNode)`
  - `fetchFirebaseLocations()`
  - `addMarker (place: FirebaseLocationObject)`

- **ARSelectionViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapCancelButton(_ sender: Any)`
  - `didTapAddButton(_ sender: Any)`
  - `setFavoriteButton()`

- **ExploreViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapCameraButton(_ sender: Any)`

- **MapViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapCameraButton(_ sender: Any)`
  - `setupAds()`
  - `reload()`
  - `didTapSettings(_ sender: Any)`
  - `didTapSearchBarButton(_ sender: Any)`
  - `goToSettings()`
  - `unwindToHomeVC(unwindSegue: UIStoryboardSegue)`
  - `initializeLocationManager()`
  - `setupMap()`
  - `locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation])`
  - `focusMap(latitude: CLLocationDegrees, longitude: CLLocationDegrees)`
  - `listLikelyPlaces()`
  - `fetchFirebaseLocations()`
  - `fetchAllFirebaseLocations()`
  - `fetchFirebaseNearbyLocations()`
  - `addMarker (location: FirebaseLocationObject, focus: Bool = false)`
  - `textFieldDidEndEditing(_ textField: UITextField)`
  - `beginSearch()`
  - `fireStoreSearch(query: String)`
  - `mapView(_ mapView: GMSMapView, didTap marker: GMSMarker)`
  - `adViewDidLoadAd(_ view: MPAdView!, adSize: CGSize)`
  - `adView(_ view: MPAdView!, didFailToLoadAdWithError error: Error!)`
  - `viewControllerForPresentingModalView() -> UIViewController?`

- **MapViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`

- **MapDrawerViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `reload()`
  - `registerViews()`
  - `showLocationDetail()`
  - `showSearchResults()`
  - `fetchLocation(documentId: String)`
  - `fetchUserById()`
  - `searchFirebase(query: String)`
  - `addAsFavorite(landmarkId: String, cell: WithFavoriteCell)`
  - `setFavoriteStatus(landmarkId: String, cell: WithFavoriteCell)`
  - `removeFromFavorites(cell: WithFavoriteCell)`
  - `numberOfSections(in tableView: UITableView) -> Int`
  - `tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int`
  - `tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell`
  - `showDetail(location: FirebaseLocationObject)`
  - `tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath)`
  - `drawerPositionDidChange(drawer: PulleyViewController, bottomSafeArea: CGFloat)`

- **SubscriptionViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapUpgradeButton(_ sender: Any)`
  - `didTapCancelButton(_ sender: Any)`
  - `fetchProducts()`
  - `productsRequest(_ request: SKProductsRequest, didReceive response: SKProductsResponse)`
  - `paymentQueue(_ queue: SKPaymentQueue, updatedTransactions transactions: [SKPaymentTransaction])`
  - `complete(transaction: SKPaymentTransaction)`
  - `restore(transaction: SKPaymentTransaction)`
  - `fail(transaction: SKPaymentTransaction)`
  - `deliverPurchaseNotificationFor(identifier: String?)`

- **FavoritesPulleyViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`

- **FavoritesViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `viewWillAppear(_ animated: Bool)`
  - `reload()`
  - `fetchFavorites()`
  - `didTapBackButton(_ sender: Any)`
  - `tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int`
  - `tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell`
  - `tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath)`

- **AccountDetailsViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `unwindToSettings(unwindSegue: UIStoryboardSegue)`
  - `logout()`
  - `goToChangePassword()`
  - `goToContactUs()`
  - `goToPrivacyPolicy()`
  - `goToAboutUs()`
  - `numberOfSections(in tableView: UITableView) -> Int`
  - `tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int`
  - `tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell`
  - `tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath)`

- **ChangePasswordViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapBackButton(_ sender: Any)`
  - `didTapResetButton(_ sender: Any)`
  - `backToSettings()`
  - `validateNewPassword() -> Bool`
  - `validateConfirmPassword() -> Bool`
  - `resetPassword()`
  - `resetPasswordAuth() -> Bool`
  - `textFieldDidEndEditing(_ textField: UITextField)`

- **PrivacyPolicyViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`

- **AboutUsViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`

- **ContactUsViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `unwindToContactUs(unwindSegue: UIStoryboardSegue)`
  - `goToRating()`
  - `goToReport()`
  - `goToSuggest()`
  - `numberOfSections(in tableView: UITableView) -> Int`
  - `tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int`
  - `tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell`
  - `tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath)`

- **RateYourExperienceViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `btn1(_ sender: Any)`
  - `btn2(_ sender: Any)`
  - `btn3(_ sender: Any)`
  - `btn4(_ sender: Any)`
  - `btn5(_ sender: Any)`
  - `didTapBackButton(_ sender: Any)`
  - `didTapDoneButton(_ sender: Any)`
  - `submitRating()`
  - `setRating()`

- **EmailFeedbackViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `submitEmail(email: [String: Any?])`
  - `success()`
  - `generateBody(content: String, rating: Int? = nil) -> String`

- **RateYourExperienceViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `btn1(_ sender: Any)`
  - `btn2(_ sender: Any)`
  - `btn3(_ sender: Any)`
  - `btn4(_ sender: Any)`
  - `btn5(_ sender: Any)`
  - `didTapBackButton(_ sender: Any)`
  - `didTapDoneButton(_ sender: Any)`
  - `submitRating()`
  - `setRating()`

- **ReportViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapDoneButton(_ sender: Any)`
  - `submitReport()`

- **SuggestViewController** - manages the app access, redirects to Login screen when user is not logged in.    
  ##### Methods
  - `viewDidLoad()`
  - `didTapDone(_ sender: Any)`
  - `submitSuggestion()`
