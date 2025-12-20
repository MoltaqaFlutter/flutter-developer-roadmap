# Task 1: Foundation, Architecture & Setup

## 🎯 Goal
Initialize the project and set up a scalable folder structure based on **Clean Architecture**. You will also analyze the UI design to plan your features.

## 📝 Tasks

### 1. Figma Analysis & Feature Planning
- [Figma Design](https://www.figma.com/design/NLUuoV9ZlKnhzK4V9dIBi7/Moltaqa-Intern---Ecommerce-Mobile-App-UI?node-id=221-117&t=fFYBVRV9VKjfrY40-1)
- **Action**: Open the provided Figma design (or use a standard E-commerce UI kit reference).
- **Task**: Identify the key features needed (e.g., Home, Product Details, Favorites, Cart).
- **Output**: A list of "Features" that will map to your project structure.

### 2. Project Initialization
- Create a new Flutter project: `flutter create mega_ecommerce_app`
- Set up the following top-level folder structure in `lib/`:
  ```
  lib/
  ├── core/           # Shared utilities, constants, errors, theme
  ├── features/       # Feature-based modules (e.g., home, cart, favorites)
  └── main.dart
  └── my_app.dart
  ```

### 3. Theming & Assets
- Define your `ThemeData` in `core/theme/`.
- Import necessary assets (images, icons) into `assets/` and register them in `pubspec.yaml`.
- Use font used in figma into `assets/fonts/` and register them in `pubspec.yaml` for help you will fint its name **[Inter](https://fonts.google.com/specimen/Inter)** and can download easly from google fonts then use.
- Make sure use app font in material to preview in whole app as figma design.
- Add figma colors **AppColors Class** and text styles **TextStyles Class**.
  ```
  EX:
  For Text : text1 , text2 , text3
  For Cards : card1 , card2 , card3
  For Button : buttonEnable , buttonDisale 
  etc ...
  ```

### 4. App Config
- Change default app name previewed to `Mega`.
- Change `App Launcher Icon` to that provided in [Figma Design](https://www.figma.com/design/NLUuoV9ZlKnhzK4V9dIBi7/Moltaqa-Intern---Ecommerce-Mobile-App-UI?node-id=221-117&t=fFYBVRV9VKjfrY40-1).
- Change `App Native Splash` to that provided in [Figma Design](https://www.figma.com/design/NLUuoV9ZlKnhzK4V9dIBi7/Moltaqa-Intern---Ecommerce-Mobile-App-UI?node-id=221-117&t=fFYBVRV9VKjfrY40-1).

### 5. Feature Structure (Clean Architecture)
For each feature (e.g., `product`), create the following sub-folders:
```
lib/features/product/
├── data/
│   ├── datasources/  # Remote/Local data sources
│   ├── models/       # JSON parsing models (extends Entity)
│   └── repositories/ # Implementation of Domain Repository
├── domain/
│   ├── entities/     # Core business objects (Pure Dart)
│   ├── repositories/ # Abstract interfaces
│   └── usecases/     # Business logic classes
└── presentation/
    ├── cubit/        # State Management
    ├── pages/        # Screens
    └── widgets/      # Reusable UI components
```

### 6. Learn more about flutter
- Make in core directory for exentions **lib/core/utils/extensions**
- Setup Internationalizing in project using [l10n](https://docs.flutter.dev/ui/internationalization)
- Set ready with **Get it** to use as di in clean architcture and use in app

## 📚 Resources

#### Clean Architcture
- [Variable X - Flutter Clean Architecture Part 1 - arabic content](https://www.youtube.com/watch?v=RHxzX_ztcBc&list=PL9uUr_gWuqBDi7AMwQ1shSM2ZCcqMW7Q0)
- [Variable X - Flutter Clean Architecture Part 2 - arabic content](https://www.youtube.com/watch?v=fDt4ZxUa4Bk&list=PL9uUr_gWuqBDi7AMwQ1shSM2ZCcqMW7Q0&index=2)
- [Omar Ahmed - Clean Architecture deep dive - بالعربي](https://www.youtube.com/watch?v=JJlS_UtlYLg&t=15s)

#### Exenstions
- [Extensions in Flutter - بالعربي  - Omar Ahmed](https://www.youtube.com/watch?v=mBeVISZoIzE)
- [Flutter Docs](https://dart.dev/language/extension-methods)

#### Internationalizing Flutter apps
- [Flutter Official Internationalizing](https://docs.flutter.dev/ui/internationalization)
- [Variable X - Flutter | Localization part 1](https://www.youtube.com/watch?v=_OFTX0mRt8c)
- [Variable X - Flutter | Localization part 2](https://www.youtube.com/watch?v=dHTbm4garuY)

#### Service Locator - Get it
- [Variable X - Service Locator](https://www.youtube.com/watch?v=FsNrNfj5jPI&list=PL9uUr_gWuqBDi7AMwQ1shSM2ZCcqMW7Q0&index=4)


