# Build apk in react native


Make sure you have already directory android/app/src/main/assets/, if not create directory, after that create new file and save as index.android.bundle and put your file in like this android/app/src/main/assets/index.android.bundle

After that run this

    npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/

    cd android && ./gradlew assembleDebug

Then you can get apk in app/build/outputs/apk/debug/app-debug.apk
