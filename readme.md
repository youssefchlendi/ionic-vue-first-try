# first ionic vue try
in this repository i'll try to use ionic vue to create a simple app,
this is my first try to use ionic vue..
### first subproject
#### creating project
1. Installing ionic globally : npm install -g @ionic/cli@latest native-run cordova-res
2. Creating new project : ionic start 'name'photo-gallery tabs `*template*`--type vue `*options*`--capacitor
3. installing "@capacitor/camera": "^4.0.1", "@capacitor/haptics": "4.0.1", "@capacitor/keyboard", "@capacitor/status-bar", "@capacitor/storage"
#### customizing project
1. change tab2 view layout, adding gallerie field and take picture button
##### ion-page
this is the main page component
##### ion-header
this is the header component
##### ion-content
this is the content component
##### ion-toolbar
this is the toolbar component
##### ion-title
this is the title component
##### ion-tab-bar
this is the tab bar component
##### ion-fab
this is the floating action button container component
##### ion-fab-button
this is the floating action button component
##### ion-icon
this is the icon component
2. creating logic .. image taking and saving .. 
3. adding mobile adaptability to the project
##### isPlatform
 import { isPlatform } from '@ionic/vue';
 - isPlatform is a function that returns true if the current platform is the given platform.
 Ex: isPlatform("hybrid") will return true if the current platform is either ios or android.
 4. building project
 4.1. ionic build 
 4.2. ionic cap add `*platform*` android
// after updating project : ionic cap copy,ionic cap sync
4.2. Open project in emulator environment : ionic cap open `*platform*` android 
