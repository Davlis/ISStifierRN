Wtyczka usług Google dla Gradle wczytuje pobrany przed chwilą plik google-services.json. Zmodyfikuj pliki build.gradle, aby użyć tej wtyczki.

Plik build.gradle na poziomie projektu (<projekt>/build.gradle):

buildscript {
  repositories {
    // Check that you have the following line (if not, add it):
    google()  // Google's Maven repository
  }
  dependencies {
    ...
    // Add this line
    classpath 'com.google.gms:google-services:4.3.3'
  }
}

allprojects {
  ...
  repositories {
    // Check that you have the following line (if not, add it):
    google()  // Google's Maven repository
    ...
  }
}

Plik build.gradle na poziomie aplikacji (<projekt>/<moduł-aplikacji>/build.gradle):

apply plugin: 'com.android.application'
// Add this line
apply plugin: 'com.google.gms.google-services'

dependencies {
  // add SDKs for desired Firebase products
  // https://firebase.google.com/docs/android/setup#available-libraries
}