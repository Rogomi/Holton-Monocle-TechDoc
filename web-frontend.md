[Back](index.md)

# Holton Monocle Web

## Technical Documentation
    
### GETTING STARTED

Holton Monocle Web Frontend was developed using JavaScript.  The frontend was developed using the Vue.JS framework.

### INSTALLATION AND DEVELOPMENT

Firstly, the user must have [Node.JS](https://nodejs.org/en/) installed. And after that, the user must follow the guide for Vue.JS [here](https://vuejs.org/guide/introduction.html#what-is-vue).
Lastly, the user must have a text editor program. The developers suggest [Visual Studio Code](https://code.visualstudio.com/).

### PROGRAMMING LANGUAGE

Holton Monocle Web uses JavaScript for development

### DEBUGGING

The developers use Chrome Dev Tools. 

##### UI Libraries
**PrimeVue** - Allows you to build complex, modern, and highly dynamic Vue applications.  

### IMPORTANT CLASSES

#### Initialization Classes
- **main.js** - handles the initialization of Vue components
- **router.js** - handles the navigation of pages
- **apiService.js** - handles the navigation 

#### Components

- **LoginForm.vue** - handles the login page
  - `handleResponse()`
- **ForgotPassForm.vue** - handles the forgot password page

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


### ARCHITECTURE USED

Holton Monocle Android follows and uses the Model-View-ViewModel Architecture (MVVM). It consists of an xml file which is the UI layout definition for the screen, a Fragment that is the UI controller that displays the data, and the ViewModel, a class that prepares the data for viewing in the Fragment and reacts to user interactions.

[here](https://drive.google.com/file/d/1ikD6dEHvLZIGkIyTN_1Zs-iRh_RnZbgy/view?usp=sharing)
