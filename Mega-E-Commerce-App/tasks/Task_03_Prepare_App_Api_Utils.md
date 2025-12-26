# Task 3: Prepare App Api Utils

## 🎯 Goal
Prepare app api utils like failure , api service , dio , exeption handlers

## 📝 Tasks

### 1. Add failures and execptions
- Add lib/core/network/
- Add in failure.dart , execptions.dart then manage its content.
- Make interface ApiHelper that has [ get , post , delete , put ] functions and implement it as DioApiHelper that will implement logic for its functions using dio to use in our app

### 2. Work on Api For Authentication
- **Action**: make authentcaion feauture using clean architcure
- **Task**: Make auth features and mange ui with cubit and manage loading , failure , success actions
- **📚 Resources**:
  - You can find easly more about [Authentication Api here](../api_tasks/01_authentication.md).
  - You can get [Postman Collection](../postman/mega_ecommerce_backend.postman_collection.json).
  - Read more about api from [Here](../api_tasks/README.md).

### 2. Cache Logged User && Token
- Add lib/core/data/data_source/cached_authenticated_data_source.dart
- Add lib/core/data/domain/cached_authenticated_repository.dart
- **Task**: 
  - Add [flutter_secure_storage](https://pub.dev/packages/flutter_secure_storage) and use for cache sensitive data
  - Make class TokenEntity that represent cahed token in domain and TokenModel in data extends from TokenEntity
  - Also make class CachedUserEntity that represent cache for requied user data [like id,name,..] in domain and CachedUserModel in data extends from CachedUserEntity
  - Make cache authenticated user required files in code in location mentioned above
  - Include cached_authenticated_repository , cached_authenticated_repository_imp and cached_authenticated_data_source 
  - Dont miss use cases for cached authenticated
  - Use TokenEntity and CachedUserEntity as returned values in cached_authenticated_repository and its use cases

  