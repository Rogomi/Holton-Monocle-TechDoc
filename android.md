[Back](index.md)

# Holton Monocle Android

## Technical Documentation

### GETTING STARTED

Holton Monocle Android was developed using Android Studio. This project uses Kotlin as the Programming Language, Android Studio Layout Editor for the Interface, and Gradle for connecting different Third-Party Libraries. The target and compiled SDK Version is 30 with a minimum SDK version of 26.
For more information on the IDE and system requirements to enable you to work on the source code, it is available [here](https://developer.android.com/)

### INSTALLATION AND DEVELOPMENT

In order to start the development, first you need to start Android Studio. Import the Holton Monocle project and then wait for the build to finish.

### PROGRAMMING LANGUAGE

Holton Monocle Android uses Kotlin for development

### MINIMUM VERSION

Holton Monocle can run on Android Systems with minimum SDK version 26. It may encounter multiple issues on lower SDKversions.

### APPLICATION ID

com.holton.monocle

### DEBUGGING

We use a few debugging tools to test Holton Monocle functionalities.
We also use Android Virtual Device in Android Studio in order to test the Native Apps in different screen sizes and SDK Versions. 

### THIRD-PARTY LIBRARIES

Most of the third-party libraries are integrated using Gradle. They can be added by searching library names found in the Dependencies tab in the Project Structure window.

##### Important Libraries
**Android Lifecycle** - Used to manage data and connections between activities and fragments.
**RxAndroid and RxJava** - Used to connect to a network and manage data.
**Google Play Services** - Used for ARCore and Auto-update features.
**Google ARCore** - Used for ARCamera.
**Google Maps** - Used for Locations.

##### Firebase Platform Libraries.
**Firebase/Analytics** - Used for App Analytics.
**Firebase/Crashlytics** - Used to identify causes of crashes from users.
**Firebase/Performance** - Used to monitor app performance.
**Firebase/Firestore** - Used to store user and landmark data.

##### UI Libraries
**Glide** - Used for displaying images.
**Android Spinkit** - Used for showing a circular loading display.

##### Other Useful Libraries 
**Android Navigation: Kotlin** - Used to manage connections between different screens and layouts.
**Esperando** - Used to connect shared data between activies.
**Dagger-Hilt** - Used for easier data management between activities.
**Karumi/Dexter** - Used to simplify permission requests and access.
**Google Billing** - Used for monetization and payment for services.
**Mopub Ads** - Used for monetization.

### IMPORTANT CLASSES

#### Activities/Fragments

- **MainActivity** - handles the main activity container which will display all the core.
  ##### Fragment/ViewModel Methods

- **SplashScreen Fragment** - handles the display for loading the splashscreen for 2 seconds.
  ##### Fragment/ViewModel Methods
  - `startSplash()`

- **Login Fragment** - handles the display where users will input their account and password or sign in via google or apple.
  ##### Fragment/ViewModel Methods
  - `firebaseAuthWithGoogle()`
  - `signIn()`
  - `checkUserDocuments()`
  - `addUserToFirestore()`
  - `applePending()`
  - `appleAuth()`
  - `goToHome()`
  
- **Sign Up Fragment** - handles the display where users can sign up their accounts or sign-in via google or apple.
  ##### Fragment/ViewModel Methods
  - `initSignUp()`
  - `firebaseAuthWithGoogle()`
  - `createAccount()`
  - `signIn()`
  - `checkUserDocuments()`
  - `addUserToFirestore()`
  - `applePending()`
  - `appleAuth()`
  - `goToHome()`

- **Reset Password Fragment** - handles the display for the user to reset their password.
  ##### Fragment/ViewModel Methods
  - `resetPassword()`
  - `showCheckMail()`
  - `goToGmail()`

- **Main Nav Fragment** - handles the bottom navigation bar.
##### Fragment/ViewModel Methods
  - `initNavigation()`
  
- **Explore Fragment** - handles the display for maps, ar, and ads.
  ##### Fragment/ViewModel Methods
  - `initAdBanner()`
  - `onRenderNearbyLandmarks()`
  - `onRenderSearchedLandmarks()`
  - `loadLandmarksPin()`
  - `checkPermissions()`
  - `checkIfGpsEnabled()`
  - `getDistanceInMiles()`
  - `initMap()`
  - `getCurrentLocation()`
  - `resumeArCamera()`
  - `pauseArCamera()`
  - `showArCamera()`
  - `renderVenues()`
  - `setupSession()`
  - `setupAndRenderVenuesMarkers()`
  - `updateVenuesMarkers()`
  - `attachMarkerToScene()`
  - `detachMarker()`
  - `search()`
  - `loadNearbyLandmarks()`

- **LocationDetails Dialog Fragment** - handles the display when user taps a landmark.
  ##### Fragment/ViewModel Methods
  - `updateButton()`
  - `initFavoriteButton()`
  - `initLocationDetailsAdapter()`
  - `addToFavorites()`
  - `checkIfFavorite()`

- **Search Dialog Fragment** - handles the display when user taps a landmark.
  ##### Fragment/ViewModel Methods
  - `initSearchAdapter()`
  - `checkFavorites()`
  - `addBookmark()`
  - `showDetails()`
  - `addToFavorites()`
  - `checkIfFavorite()`
  
- **Favorites Fragment** - handles the display of the user's favorited landmarks.
  ##### Fragment/ViewModel Methods
  - `initFavoriteAdapter()`
  - `getMyFavorites()`

- **Settings Fragment** - handles the display for app's settings. This includes change password, upgrade plan, privacy policy, contact us, and about the app.
  ##### Fragment/ViewModel Methods
  - `initBillingClient()`
  - `upgradeToPremium()`
  - `initDetails()`
  - `onPurchasesUpdated()`
  
- **Change Password Fragment** - handles the display the user to be able to change their password. By default, third party accounts cannot change password.
  ##### Fragment/ViewModel Methods
  - `initActions()`
  - `getOldPassword()`
  - `initupdatePasswordActions()`
  - `updatePassword()`

- **Upgrade Fragment** - handles google pay integration for the app.
  ##### Fragment/ViewModel Methods
  - `initBillingClient()`  
  - `initPremium()`  
  - `initLabels()`  
  - `launchPurchaseFlow()`  
  - `onPurchasesUpdated()`  
  - `checkPurchases()`  
  - `upgradeToPremium()`  

- **Privacy Fragment** - handles the display of privacy policy.
  ##### Fragment/ViewModel Methods

- **Contact Us Fragment** - handles the display of contact us navigation tabs: suggest something, report an issue, rate your experience.
  ##### Fragment/ViewModel Methods

- **SuggestSomething Fragment** - handles the display for suggest something.
  ##### Fragment/ViewModel Methods
  - `sendEmail()`  

- **Report Issue Fragment** - handles the display for report an issues.
  ##### Fragment/ViewModel Methods
  - `sendEmail()`  

- **Experience Fragment** - handles the display for rate your experience.
  ##### Fragment/ViewModel Methods
  - `sendEmail()` 

- **About The App Fragment** - handles the display of about the app.
  ##### Fragment/ViewModel Methods


### APPLICATION DIAGRAM

[here](https://drive.google.com/file/d/1s2uI8Yv_OeTRbzJL0wV38KEIyBPhwlfn/view?usp=sharing)

### ARCHITECTURE USED

Holton Monocle Android follows and uses the Model-View-ViewModel Architecture (MVVM). It consists of an xml file which is the UI layout definition for the screen, a Fragment that is the UI controller that displays the data, and the ViewModel, a class that prepares the data for viewing in the Fragment and reacts to user interactions.

[here](https://drive.google.com/file/d/1ikD6dEHvLZIGkIyTN_1Zs-iRh_RnZbgy/view?usp=sharing)
