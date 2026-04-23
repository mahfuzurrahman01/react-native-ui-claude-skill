# react-native-ui-ux

<p align="left">
  <img src="https://res.cloudinary.com/dka0q8f82/image/upload/v1776888959/Screenshot_2026-04-23_at_02.10.33_tliuac.png" width="48%" />
  <img src="https://res.cloudinary.com/dka0q8f82/image/upload/v1776919332/Screenshot_2026-04-23_at_10.41.55_soxnjv.png" width="48%" />
</p>

A Claude skill for building React Native UIs that don't look AI-generated.

Drop this skill into Claude and it stops producing the usual generic mobile UI — the boxy cards, the hardcoded hex colors, the same layout no matter what the app actually is. Instead, Claude behaves like a senior mobile engineer: it asks about your product first, builds a token-based theme before any screen, and ships code that respects iOS and Android idioms separately.

## What it does

- **Runs a short discovery interview** before writing UI code for a new app. A meditation app and a trading app shouldn't look the same — this skill makes sure they don't.
- **Enforces a token-based theme** (primitives → semantic tokens → `useTheme()` hook). No hardcoded colors in screen files.
- **Handles dark mode properly** — elevation via surface lightness, desaturated brand colors, warm near-black instead of `#000`.
- **Writes platform-correct code** — Android ripple vs iOS opacity, shadow vs elevation, `SafeAreaView` on every screen, 44/48pt touch targets.
- **Catches common anti-patterns** — light gray text on white, `TouchableOpacity` with no feedback, placeholder-as-label, mixed component libraries.
- **Accessibility by default** — labels, roles, contrast ratios, reduce-motion handling.

## Install

Place the `SKILL.md` file at `~/.claude/skills/react-native-ui-ux/SKILL.md` (or wherever your Claude environment loads user skills from). Claude will pick it up automatically whenever a request touches React Native UI.

## When it triggers

Any mention of React Native screens, components, theming, navigation, dark mode, animations, haptics, or "make this prettier" on a mobile app. Also when you describe a product idea and ask for the UI to be built.

## Philosophy

Generic AI-looking UIs are a failure mode. The small details — warm grays with a warm brand, pill buttons with haptics, a live dot that breathes at 1.8s — are what make an app feel designed. This skill encodes those details so Claude doesn't skip them.
