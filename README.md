# Expo Camera Preview Issues with Conditional Rendering

This repository demonstrates a bug in Expo's Camera API when used within a conditionally rendered component. The camera preview may not render correctly, or may throw errors, if the component is unmounted and remounted. This often happens with navigation changes or frequent parent component re-renders.

## Bug Reproduction

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the app: `expo start`
4. Navigate between screens to trigger the component unmount/remount cycle. Observe that the camera preview may fail to render or throw errors.

## Bug Solution

The provided solution uses a `useRef` hook to persist the camera object across component re-renders. This prevents the camera from being repeatedly initialized and destroyed, thereby resolving the preview issues.  Additional error handling is also implemented.

## Note:

This bug is specific to situations where the component containing the Expo Camera is unmounted and remounted. If the component remains mounted, the bug will not be observed.