# Expo Linking.getInitialURL() returns null on Android inconsistently

This repository demonstrates a bug in the Expo `Linking` API on Android where `getInitialURL()` sometimes returns `null` even when a deep link has been opened.  This inconsistent behavior makes it unreliable to handle deep links during the initial app launch.

## Bug Reproduction

1. Clone this repository.
2. Run the app on an Android device or emulator.
3. Open a deep link that's configured to target the app.
4. Observe that `getInitialURL()` may return `null` in some instances, despite the deep link being successfully opened.

## Solution

The solution involves checking multiple times and potentially adding a delay to ensure `getInitialURL()` successfully retrieves the URL.  It's not an ideal solution as it adds complexity and reliance on heuristics, but it's a workaround for the inconsistent behavior.