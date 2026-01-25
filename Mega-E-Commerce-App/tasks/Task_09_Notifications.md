# Task 3: notifications

## 🎯 Goal
Manage notifications system for whole app.

## 📝 Tasks

### 1. Make Cart
- **Api**
you can find api services here
  [Swager_API](https://mega155-ecommerce-app-backend.vercel.app/api-docs/#/)

- **Task**:
  - Contact with api owner to add your email app firebase project to link inside app.
  - You can find steps claify to setup and add in [Flutter fire docs](https://firebase.flutter.dev/docs/messaging/overview)
  make sure to read them and work from them
  - Add required dependances to app like [firebase_core](https://pub.dev/packages/firebase_core) && [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications) && [firebase_messaging](https://pub.dev/packages/firebase_messaging)
  - Setup dependances and add configs if need as its docs.
  - Make class name **FirebaseHelper** that has function named init called in main function for app to initialize required for firebase && premissins.
  - Add inside **FirebaseHelper** class all required data and steps for this feature.
  - Make notifications main page as in design and get data from api.
  - Manage notification tap action for each case.
  - Understand topics in firebase and how it work.
  - Add subscripe for **Announcements** topic to recive notiications for.

- **Notification Cases**:
  - Generic notification from admin for all users , do nothing.
  - On checkout order recive confirm notification opens order details page.
  - On Admin action for user being as store request like accept or reject.
  - On chat messages from other users while user not in chat room that on tap on opens chat detaile page.
  - On Announcements for products that opens product details page.

- **How to test**:
You can test api sends notifications With admin credionals via
[This Api](https://mega155-ecommerce-app-backend.vercel.app/api-docs/#/Notifications/post_api_notifications_send)