# Windows Single Instance
1. Add `WidgetsFlutterBinding.ensureInitialized();` to the start of your apps `main` function.
1. Add the `async` modifier to your apps `main` function.
1. Add a call to `WindowsSingleInstance.ensureSingleInstance()`, passing the apps startup args, a custom app string unique to your app (a-z, 0-9, \_ and - only), and an optional callback function.

```yaml
  libw_instance:
    git:
      url: https://github.com/ng-huy/libw_instance.git
      ref: main
```

```dart
var appId = "com.example.singleapp";
void main(List<String> args) async {
    WidgetsFlutterBinding.ensureInitialized();
    await WindowsSingleInstance.ensureSingleInstance(
        args,
        appId,
        onSecondWindow: (args) {});
    runApp(const MyApp());
}
```
