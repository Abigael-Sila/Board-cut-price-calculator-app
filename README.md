# Board Calculator App for Onyi's Interior Design

A simple, offline calculator app for quickly determining the price of board portions based on dimensions.

## Features

- **Quick Price Calculation**: Calculate prices based on board type and piece dimensions
- **Board Management**: Add, edit, and delete board types with full price and dimensions
- **Calculation History**: View recent calculations with timestamps
- **PIN Protection**: Admin features protected by PIN code
- **Offline First**: All data stored locally, works without internet

## Default Board Types

The app comes pre-loaded with common board types:
- 18mm MDF (KES 4,500)
- 12mm Plywood (KES 3,800)
- 15mm Blockboard (KES 5,200)
- 18mm Chipboard (KES 3,200)

All boards default to 2440mm × 1220mm dimensions.

## How to Use

### Calculator Tab
1. Select a board type from the dropdown
2. Enter the piece length and width in millimeters
3. Tap "Calculate Price"
4. View the calculated price and details

### History Tab
- View all past calculations
- See calculation details and timestamps
- Clear history when needed

### Manage Boards Tab
- View all board types
- Add new board types (PIN required)
- Edit existing boards (PIN required)
- Delete boards (PIN required)

## PIN Protection

The first time you try to add, edit, or delete a board, you'll be asked to create a 4-digit PIN. This PIN protects your board pricing data from unauthorized changes.

**Important**: Remember your PIN! There is no recovery method built into the app.

## Building for Android

Since this app is built with React Native Expo, you have several options to build an APK:

### Option 1: EAS Build (Recommended)

1. Install EAS CLI:
   ```bash
   npm install -g eas-cli
   ```

2. Login to Expo:
   ```bash
   eas login
   ```

3. Configure the build:
   ```bash
   eas build:configure
   ```

4. Build APK:
   ```bash
   eas build --platform android --profile preview
   ```

5. Download the APK from the link provided after the build completes

### Option 2: Local Build with Android Studio

1. Install Android Studio and set up the Android SDK

2. Export to native code:
   ```bash
   npx expo prebuild
   ```

3. Open the `android` folder in Android Studio

4. Build APK:
   - Go to Build > Build Bundle(s) / APK(s) > Build APK(s)
   - Find the APK in `android/app/build/outputs/apk/`

### Option 3: Expo Application Services (Web)

1. Create an Expo account at https://expo.dev
2. Push your code to a git repository
3. Use EAS Build from the web dashboard
4. Download the generated APK

## Installing on Android Devices

1. Transfer the APK file to the Android device
2. Enable "Install from Unknown Sources" in device settings:
   - Settings > Security > Unknown Sources (enable)
   - Or: Settings > Apps > Special Access > Install Unknown Apps
3. Open the APK file and tap "Install"

## Technical Details

- **Framework**: React Native with Expo SDK 54
- **Storage**: AsyncStorage for local data persistence
- **Navigation**: Expo Router (file-based routing)
- **Platform**: Android-first (works on web for testing)

## Price Calculation Formula

```
Price per mm² = Full Board Price / (Full Length × Full Width)
Final Price = Price per mm² × (Piece Length × Piece Width)
```

Example:
- Board: 18mm MDF, KES 4,500, 2440mm × 1220mm
- Piece: 1000mm × 500mm
- Price = 4500 / (2440 × 1220) × (1000 × 500) = KES 755

## Support

For issues or questions, contact the development team.
"# Board-cut-price-calculator-app" 
