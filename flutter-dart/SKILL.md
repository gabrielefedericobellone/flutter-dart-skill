---
name: flutter-dart
description: Create distinctive, production-grade Flutter UI and Dart code with high design quality. Use this skill whenever the user asks to build Flutter widgets, screens, pages, or app features in .dart files (examples include screens, custom widgets, navigation, state management, forms, animations, or any Flutter/Dart component). Also use when styling, refactoring, or improving existing .dart code. Generates polished, idiomatic Flutter code that avoids generic boilerplate aesthetics.
---

This skill guides creation of distinctive, production-grade Flutter interfaces and Dart code. Implement real, working `.dart` files with strong attention to Flutter idioms, aesthetic polish, and architectural correctness.

The user provides Flutter requirements: a widget, screen, feature, or Dart utility to build. They may include context about the app's purpose, target platform (iOS/Android/web/desktop), or technical constraints.

---

## Design Thinking (before coding)

Before writing any Dart, understand the context and commit to a clear aesthetic and architectural direction:

- **Purpose**: What does this screen/widget do? Who uses it and in what context?
- **Tone**: Pick a direction: ultra-minimal Material 3, bold dark-mode, soft pastel iOS-like, high-contrast accessibility-first, playful/gamified, editorial/content-heavy, data-dense dashboard, etc.
- **State complexity**: Does this widget need local state (`StatefulWidget`/`ValueNotifier`) or external state (Provider, Riverpod, Bloc, etc.)?
- **Reusability**: Is this a one-off screen or a composable, reusable component?
- **Differentiation**: What will make this widget feel truly crafted, not generated?

**CRITICAL**: Commit to a clear direction. Thoughtful minimalism and rich maximalism both work — the key is intentionality and consistency throughout the widget tree.

---

## Flutter Code Guidelines

### Widget architecture
- Prefer `StatelessWidget` whenever possible; introduce `StatefulWidget` only when local mutable state is genuinely needed.
- Split large builds into focused private widgets (`_HeaderSection`, `_ItemCard`, etc.) instead of a monolithic `build` method.
- Use `const` constructors aggressively — it's free performance.
- Follow the single-responsibility principle per widget.

### Dart style
- Follow [Effective Dart](https://dart.dev/guides/language/effective-dart) conventions.
- Use named parameters with `required` for clarity on all non-trivial constructors.
- Prefer `final` and immutable data structures; use `copyWith` patterns for state updates.
- Use null safety correctly — avoid `!` force-unwrap unless you can guarantee non-null.
- Leverage Dart 3 features: records, patterns, sealed classes where appropriate.

### Theming & colors
- Always use `Theme.of(context)` color roles (`colorScheme.primary`, `colorScheme.surface`, etc.) rather than hardcoded hex colors.
- Define a `ThemeData` with a full `ColorScheme` if the feature requires it — don't scatter raw `Color(0xFF...)` values.
- Support dark mode from the start unless explicitly told not to.

### Typography
- Use `Theme.of(context).textTheme` roles (`displayLarge`, `titleMedium`, `bodySmall`, etc.) for semantic sizing.
- Choose a distinctive `GoogleFonts` pairing when the design calls for character — avoid defaulting to the system font when visual identity matters.
- Maintain clear type hierarchy: one dominant display style, one body style, one label style.

### Spacing & layout
- Use a consistent spacing scale (multiples of 4 or 8 dp): `8, 12, 16, 24, 32, 48`.
- Prefer `Padding` + `Column`/`Row` over `SizedBox` for semantic spacing.
- Use `SafeArea` on top-level screens; handle keyboard insets with `resizeToAvoidBottomInset` or `Padding` where needed.
- Leverage `Flexible`, `Expanded`, and `Spacer` intentionally — avoid hardcoded heights that break on different screen sizes.

### Animations & micro-interactions
- Use `AnimatedContainer`, `AnimatedOpacity`, `AnimatedSwitcher` for simple state-driven transitions.
- Use `TweenAnimationBuilder` or explicit `AnimationController` for custom curves.
- Add meaningful page transitions via `PageRouteBuilder` or `go_router` custom transitions.
- A single well-orchestrated entrance animation beats scattered micro-interactions.

### Navigation
- Use `go_router` for anything beyond trivial navigation (preferred in modern Flutter).
- Keep route definitions centralised in a `router.dart` file.
- Pass data via route extras or constructor params — avoid global mutable state for navigation data.

### Performance
- Use `ListView.builder` / `SliverList` for long lists — never build the full list eagerly.
- Cache expensive computations; avoid rebuilding subtrees unnecessarily by splitting widgets.
- Use `RepaintBoundary` around frequently-updating widgets (animations, clocks, live data).

---

## File output conventions

- One primary widget or feature per `.dart` file.
- Filename in `snake_case` matching the main class: `user_profile_screen.dart`, `animated_card.dart`.
- Imports ordered: dart SDK → flutter SDK → pub packages → relative project imports.
- Always include a `// TODO:` comment where integration with real data sources or navigation is expected, to guide the user.

---

## What to NEVER do

- Don't hardcode colors as raw hex — use `ThemeData` / `ColorScheme`.
- Don't write a 300-line `build()` method — decompose into sub-widgets.
- Don't use `MediaQuery.of(context).size` for every spacing decision — use layout widgets.
- Don't ignore accessibility: add `Semantics` labels on interactive or image widgets.
- Don't produce generic boilerplate that looks auto-generated — every widget should feel deliberately designed.

---

## Example deliverables this skill covers

- Custom screens (login, home, detail, settings, onboarding)
- Reusable widget components (cards, buttons, bottom sheets, dialogs, chips)
- Animated UI elements (hero transitions, shimmer loaders, animated FABs)
- Form widgets with validation
- Navigation setup with `go_router`
- `ThemeData` + `ColorScheme` definitions
- Utility Dart classes and extensions
- State management boilerplate (Riverpod providers, Bloc events/states)
