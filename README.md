# flutter-dart-skill

A Claude Code skill that generates production-grade Flutter widgets and screens in idiomatic Dart.

Instead of generic boilerplate, you get thoughtfully designed `.dart` files with proper architecture, Material 3 theming, animations, and accessibility — ready to drop into your project.

## What it covers

- Screens and full-page layouts
- Reusable widgets (cards, buttons, bottom sheets, dialogs)
- Animated UI elements (transitions, loaders, micro-interactions)
- Form widgets with validation
- `ThemeData` + `ColorScheme` definitions
- Navigation setup with `go_router`
- State management boilerplate (Riverpod, Bloc)
- Utility Dart classes and extensions

## Installation

In Claude Code, run these two commands:

```
/plugin marketplace add gabrielefedericobellone/flutter-dart-skill
/plugin install flutter-dart@flutter-dart-skills
```

## Usage

Once installed, Claude loads the skill automatically when you work on Flutter files. You can also invoke it directly:

```
/flutter-dart
```

Or just ask naturally — *"create a login screen"*, *"build an animated stats card"*, *"add a bottom sheet for filters"* — and Claude will apply the skill on its own.

## Requirements

- Claude Code
- A Flutter project with `google_fonts` in `pubspec.yaml` (for font features)

## Example output

Asking *"create an activity stats card with animated progress bars"* produces a fully decomposed, dark-themed `StatefulWidget` with staggered entrance animations, a `ColorScheme`-based theme, and `DM Sans` / `DM Mono` typography — no hardcoded colors, no monolithic `build()` methods.
