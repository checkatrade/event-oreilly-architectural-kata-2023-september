# Cross-Platform Mobile Framework

## Status

accepted

## Context

The requirements dictate both a mobile app and web app ([#R1](../../problem/requirements.md)). We wish to provide a "rich" user experience that encompasses native capabilities where available. The mobile market suggests we ought to support iOS and Android. 

## Decision

Use a framework which offers native compilation for both Android and iOS, as well as a web app. For example, [React Native](https://reactnative.dev/) with [Expo](https://expo.io/).

## Rationale

### Pros

- Embrace native functionality
- Encourage code re-use
- Potentially greater consistency in implementation across platforms

### Cons

- Can be performance challenges from cross-platform abstraction overhead with some frameworks (e.g. [Xamarin](https://luismts.com/xamarin-code-quality-performance/) / [MAUI](https://www.diva-portal.org/smash/get/diva2:1769472/FULLTEXT01.pdf))
- Abstractions make potentially limit more unique or cutting edge platform-specific features
- May result in narrower tooling options
- Delayed support for emerging native features vs true native implementations

## Consequences

The App will be developed in a cross platform framework that compiles to both native and web apps.
