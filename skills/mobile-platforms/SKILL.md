---
name: mobile-platforms
description: Master iOS and Android development with Swift, Kotlin, React Native, and Flutter. Build native and cross-platform mobile applications with modern practices.
---

# Mobile Development Platforms

## Quick Start

### Swift & SwiftUI (iOS)
```swift
import SwiftUI

struct ContentView: View {
    @State private var count = 0

    var body: some View {
        VStack {
            Text("Count: \(count)")
                .font(.title)
            Button("Increment") {
                count += 1
            }
            .buttonStyle(.borderedProminent)
        }
        .padding()
    }
}
```

### Kotlin & Jetpack Compose (Android)
```kotlin
@Composable
fun CounterApp() {
    var count by remember { mutableStateOf(0) }

    Column(
        modifier = Modifier.padding(16.dp)
    ) {
        Text("Count: $count", style = MaterialTheme.typography.headlineSmall)
        Button(onClick = { count++ }) {
            Text("Increment")
        }
    }
}
```

### React Native
```javascript
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';

export default function App() {
  const [count, setCount] = useState(0);

  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Count: {count}</Text>
      <Button title="Increment" onPress={() => setCount(count + 1)} />
    </View>
  );
}
```

### Flutter (Dart)
```dart
class CounterApp extends StatefulWidget {
  @override
  State<CounterApp> createState() => _CounterAppState();
}

class _CounterAppState extends State<CounterApp> {
  int count = 0;

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('Count: $count'),
        ElevatedButton(
          onPressed: () => setState(() => count++),
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

## Platform Comparison

| Aspect | iOS (Swift) | Android (Kotlin) | React Native | Flutter |
|--------|------------|-----------------|--------------|---------|
| Performance | Excellent | Excellent | Good | Excellent |
| Learning Curve | Medium | Medium | Easy | Medium |
| Code Sharing | Limited | Limited | High (JS) | High (Dart) |
| Ecosystem | Mature | Mature | Large | Growing |
| Time to Market | Medium | Medium | Fast | Fast |

## Key Topics

### iOS Development
- Swift language fundamentals
- SwiftUI for modern UI
- Navigation & routing
- State management
- Core Data persistence
- Network requests & URLSession
- Testing (XCTest, Swift Testing)
- App Store submission

### Android Development
- Kotlin language fundamentals
- Jetpack Compose for modern UI
- Navigation Component
- ViewModel & state management
- Room database persistence
- Retrofit for networking
- Unit & instrumented testing
- Google Play Store deployment

### Cross-Platform (React Native)
- Component structure
- Navigation libraries (React Navigation)
- State management (Redux, Zustand)
- Native module bridges
- Performance optimization
- Platform-specific code
- Testing frameworks

### Flutter/Dart
- Dart language fundamentals
- Widget system & composition
- State management (Provider, BLoC, Riverpod)
- Navigation & routing
- Data persistence
- Firebase integration
- Plugin development
- Platform channels

### Mobile UI/UX
- Material Design (Android)
- Human Interface Guidelines (iOS)
- Responsive layouts
- Touch interactions & gestures
- Accessibility features
- Dark mode support
- Animation & transitions

### Mobile Services Integration
- Local storage & databases
- APIs & REST integration
- Authentication (Firebase Auth, OAuth)
- Push notifications
- Analytics & monitoring
- Crash reporting
- Offline capabilities

### App Store Submission
- iOS App Store guidelines
- Google Play Store guidelines
- App signing & certificates
- Version management
- Release notes & descriptions
- App icons & screenshots
- Beta testing programs

## Best Practices

1. **Architecture**
   - MVVM or MVC patterns
   - Separation of concerns
   - Dependency injection
   - Clean code principles
   - Modular design

2. **Performance**
   - Memory management
   - Battery optimization
   - Network efficiency
   - UI rendering optimization
   - App size reduction

3. **Testing**
   - Unit tests
   - UI/Integration tests
   - Performance testing
   - Device testing
   - Beta user feedback

4. **User Experience**
   - Responsive design
   - Intuitive navigation
   - Fast load times
   - Offline support
   - Accessibility compliance

## Frameworks & Tools

**iOS**: Xcode, SwiftUI, Combine, Core Data
**Android**: Android Studio, Jetpack, Kotlin Coroutines
**React Native**: Expo, React Navigation, Firebase
**Flutter**: Flutter SDK, GetX, Riverpod

## Advanced Resources

- Swift: https://swift.org
- Android: https://developer.android.com
- React Native: https://reactnative.dev
- Flutter: https://flutter.dev

## Related Skills

- ios-swift-development - Swift and SwiftUI deep dive
- android-kotlin-development - Kotlin and Jetpack
- react-native - React Native specific patterns
- flutter-development - Dart and Flutter framework
- mobile-backend-integration - APIs and services
- app-store-deployment - Publishing and distribution
