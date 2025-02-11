# flutter-analytics
Services for adding analytics tools to flutter applications


In your di.dart
```final getIt = GetIt.instance;
Future<void> init() async {

  getIt.registerSingletonAsync<BranchService>(() async {
    final service = BranchService();
    await service.init();
    return service;
  });
```
Usage:
```
getIt<BranchService>().login(user.uid);
getIt<BranchService>().trackingEvents(
    "Login success",
    "User login success", {
        "user_id": user.uid,
        "user_email": user.email,
        "user_name": user.name,
    },
    BranchStandardEvent.LOGIN);
```
