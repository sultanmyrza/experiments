### Minimal reproducible example

https://github.com/sultanmyrza/experiments/tree/experiment-expo-audio

### Sumary 

`expo-audio` can play mp3 files on Android, however it cannot play on iOS. Tested on physical devices.

### Steps to reproduce

- [init expo app](https://github.com/sultanmyrza/experiments/commit/585ad1773a437628e7af5d53dbfb723a294c3ffd)
- [setup development build](https://github.com/sultanmyrza/experiments/commit/df339228c1345b4fb380d607771b1f252aaaa28c)
- [install expo-audio](https://github.com/sultanmyrza/experiments/commit/d14f4483ee424f580f6c1b33305d389227e85154)
- [play sample sound](https://github.com/sultanmyrza/experiments/commit/57416afc1292edd9b649333d5eedacc8bdd5724a)

### Reproducible Example

- https://github.com/sultanmyrza/experiments/commits/experiment-expo-audio/

### Basic Usage of expo-audio

```tsx
import { useAudioPlayer, useAudioPlayerStatus } from 'expo-audio';

const sampleAudio = require("@/assets/sounds/sample-audio.mp3");

export default function HomeScreen() {
  const player = useAudioPlayer(sampleAudio);
  const status = useAudioPlayerStatus(player);

  return (
    <Button
      title={status.playing ? "Pause Sample Sound" : "Play Sample Sound"}
      onPress={() => (status.playing ? player.pause() : player.play())}
    />
  );
}
```

### Demo Preview

https://github.com/user-attachments/assets/9fea8b25-8d1c-4255-bd92-d09360de0f77

https://github.com/user-attachments/assets/8a047c54-0bef-405f-99f9-0e508810f5a7

https://github.com/user-attachments/assets/e7a078c7-ed4e-45bb-828b-0351e2a46e92


### Environment

```text
expo-env-info 2.0.7 environment info:
    System:
      OS: macOS 26.1
      Shell: 5.9 - /bin/zsh
    Binaries:
      Node: 22.18.0 - ~/.nvm/versions/node/v22.18.0/bin/node
      Yarn: 4.9.2 - ~/.nvm/versions/node/v22.18.0/bin/yarn
      npm: 10.9.3 - ~/.nvm/versions/node/v22.18.0/bin/npm
    Managers:
      CocoaPods: 1.16.2 - /Users/sultanmyrza/.rvm/gems/ruby-3.4.5/bin/pod
    SDKs:
      iOS SDK:
        Platforms: DriverKit 25.0, iOS 26.0, macOS 26.0, tvOS 26.0, visionOS 26.0, watchOS 26.0
      Android SDK:
        API Levels: 28, 29, 31, 32, 33, 34, 35, 36
        Build Tools: 30.0.3, 33.0.1, 35.0.0, 36.0.0
        System Images: android-36 | Google Play ARM 64 v8a
    IDEs:
      Xcode: 26.0.1/17A400 - /usr/bin/xcodebuild
    npmPackages:
      expo: ~54.0.11 => 54.0.11 
      expo-router: ~6.0.9 => 6.0.9 
      react: 19.1.0 => 19.1.0 
      react-dom: 19.1.0 => 19.1.0 
      react-native: 0.81.4 => 0.81.4 
      react-native-web: ~0.21.0 => 0.21.1 
    npmGlobalPackages:
      eas-cli: 16.19.3
    Expo Workflow: managed
```

### Expo Doctor Diagnostics

```text
16/17 checks passed. 1 checks failed. Possible issues detected:
Use the --verbose flag to see more details about passed checks.

✖ Check for common project setup issues
The .expo directory is not ignored by Git. It contains machine-specific device history and development server settings and should not be committed.
Advice:
Add ".expo/" to your .gitignore to avoid committing local Expo state.

1 check failed, indicating possible issues with the project.
```