# Task 2: Internationalizing, Responsive

## 🎯 Goal
Prepare app folders and stracture to next work on connect and link api

## 📝 Tasks

### 1. Prepare Required Designs
- **Action**: Open figma design and explore.
- **Task**: Implement ( Authentication , App Main Page , More ) at least

### 2. Internationalizing Flutter app
- **Action**: Use i18 as localization provided by flutter.
- **Task** 
  - Setup , add and use localization in app.
  - Add lib/core/domain/repository/language_cache_repository.dart
  - Add lib/core/data/repository/language_cache_repository_imp.dart
  - Add lib/core/domain/entities/language/app_language_code_enum.dart
  - Manage save , get , clear language with [Shared Preferences](https://pub.dev/packages/shared_preferences) package
  - Dont miss usecase for save , get , clear language
  - Make cubit AppLanguageCubit that manage localization in app to get saved language and also have ablity to update language.
  - Use AppLanguageCubit state to set language in MaterialApp
- **📚 Resources**: 
  - [Offical flutter docs for internationalizing](https://docs.flutter.dev/ui/internationalization)
  - Variable x - Youtube :
    [Part 1](https://www.youtube.com/watch?v=_OFTX0mRt8c&t=1s) , 
    [Part 2](https://www.youtube.com/watch?v=dHTbm4garuY&t=1s)

### 3. Responsive Ui
- **Action**: Explore package for responsive like most popular [Screen Utils](https://pub.dev/packages/flutter_screenutil) , [Sizer](https://pub.dev/packages/sizer) , [Responsive Framework](https://pub.dev/packages/responsive_framework)
- **Task**: Setup and implement responsive in app [Responsive Framework](https://pub.dev/packages/responsive_framework).
- **📚 Resources**: 
  - Variable x - Youtube :
    - [Sizer](https://www.youtube.com/watch?v=5b9KUOX-PJs&list=PL9uUr_gWuqBCZKJuy9UExhPaCzQGbyWdz&index=4)
    - [Screen Utils](https://www.youtube.com/watch?v=QUnGwttjEKo&list=PL9uUr_gWuqBCZKJuy9UExhPaCzQGbyWdz&index=3) , 
    - Responsive Framework : [Part 1](https://www.youtube.com/watch?v=k8n-uBy-KXc&list=PL9uUr_gWuqBCZKJuy9UExhPaCzQGbyWdz&index=1) , [Part 2](https://www.youtube.com/watch?v=MTaUeGmRQZY&list=PL9uUr_gWuqBCZKJuy9UExhPaCzQGbyWdz&index=2)
  - Or you can explore package on pub.dev
