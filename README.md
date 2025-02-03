# React Native Dimensions.get('window') returns undefined in nested components

This repository demonstrates a common issue in React Native where `Dimensions.get('window')` returns `undefined` when used within nested components.

## Problem

When accessing screen dimensions using `Dimensions.get('window')` inside a component that isn't directly rendered in the main app's view hierarchy (e.g., within a modal, navigation component, or other nested structure), the result might be `undefined` initially.

This happens because the dimensions are not immediately available, leading to errors or unexpected behavior when the component attempts to use `width` and `height` before they're populated.

## Solution

The solution involves using the `useEffect` hook to handle the asynchronous nature of the `Dimensions` API.  This ensures that the component waits for the dimensions to be available before accessing them.

## Setup

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` or `yarn install`.
4. Run `npx react-native run-android` or `npx react-native run-ios` to run the app.