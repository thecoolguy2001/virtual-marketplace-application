# Virtual Marketplace Application

Virtual Marketplace is a cross-platform Flutter application designed for digital art commerce and artist discovery. It combines a curated marketplace experience with direct artist-to-buyer communication, enabling collectors to discover artwork, review artist portfolios, and connect with creators in one unified product.

## Project Overview

The application is structured as a modern, service-driven Flutter app with Firebase as its backend layer. The current implementation includes:

- **Authentication flow** powered by Firebase Authentication.
- **Marketplace discovery experience** with featured artwork and trending artists on the home screen.
- **Gallery browsing and filtering** for artwork discovery by category and price ranges.
- **Artist profile pages** that include biography content and portfolio listings.
- **In-app messaging** between users and artists for direct communication.
- **Checkout foundation** that captures billing details and outlines Stripe payment intent flow.
- **User settings** for account preferences and sign-out management.

## Core Value Proposition

Virtual Marketplace is built to make art transactions feel personal, trusted, and streamlined:

1. **For buyers**: a simple way to discover, evaluate, and purchase creative work.
2. **For artists**: a professional channel to present portfolios and engage potential collectors.
3. **For platforms/teams**: a scalable Flutter + Firebase architecture suitable for rapid iteration and multi-platform delivery.

## Technical Architecture

### Frontend
- **Framework**: Flutter (Material 3 styling)
- **State management / DI**: Provider
- **Routing**: Named route navigation

### Backend and Data
- **Firebase Core** for app initialization
- **Firebase Auth** for sign-in/session handling
- **Cloud Firestore** for user, artwork, and chat data persistence
- **Firebase Storage** dependency included for media workflows

### Commerce and Messaging
- **Stripe SDK integration path** present for payment workflows
- **flutter_chat_ui + flutter_chat_types** used for real-time chat UI components

## Feature Breakdown

### 1. Authentication and Session Management
- Entry-point authentication wrapper listens to auth state changes.
- Unauthenticated users are routed to Sign In.
- Authenticated users are routed to the marketplace home experience.

### 2. Marketplace Home
- Featured artworks are rendered from Firestore streams.
- Trending artists are surfaced in a dedicated carousel-like section.
- Bottom navigation provides quick movement between primary product areas.

### 3. Gallery and Discovery
- Grid-based artwork browsing UI.
- Filter dialog supports category and price constraints.
- Clear-filter action enables rapid reset of query conditions.

### 4. Artist Profiles and Portfolio
- Artist identity card with avatar, name, and biography.
- Portfolio listing of available artworks associated with each artist.
- Direct “Chat with Artist” action from profile context.

### 5. Real-Time Chat
- Deterministic chat ID generation for user-artist conversations.
- Chat thread auto-provisioning when first interaction is created.
- Stream-based message rendering and send pipeline.

### 6. Checkout and Payments (Foundation Stage)
- Checkout screen displays selected artwork and billing inputs.
- Stripe payment method + payment intent confirmation flow scaffolded.
- Purchase completion writes transaction metadata to Firestore.

> **Implementation note:** payment intent creation is currently mocked and requires a secure backend endpoint before production use.

## Technology Stack

- **Language**: Dart
- **Framework**: Flutter
- **Backend**: Firebase (Auth + Firestore)
- **Payments**: Stripe (client-side integration scaffold)
- **Architecture style**: Service-oriented UI modules (screens, services, models)

## Local Development Setup

### Prerequisites
- Flutter SDK (compatible with Dart SDK `^3.5.3`)
- Firebase project configured for target platforms
- FlutterFire configuration (`firebase_options.dart`) generated for your environment

### Install and Run
```bash
flutter pub get
flutter run
```

### Recommended Validation Commands
```bash
flutter analyze
flutter test
```

## Roadmap Recommendations

To elevate the project toward production readiness, recommended next steps include:

- Implement secure backend payment-intent creation and webhooks.
- Add complete sign-up, account recovery, and profile editing flows.
- Introduce robust authorization/security rules for Firestore.
- Add media upload workflows and moderation lifecycle.
- Improve observability (analytics, error monitoring, performance tracing).
- Expand test coverage (unit, widget, integration, and end-to-end).

## Presentation

- Project walkthrough/demo: https://www.youtube.com/watch?v=vS1hiucmQOg

---

If you are evaluating this repository for extension, this codebase provides a strong functional prototype and an excellent base for a full-featured creator commerce platform.
