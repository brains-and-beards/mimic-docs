# Integrations

Mimic app is good solution for mobile developers which want to write automatic and integration tests for application. They can do this without any testing database and testing api.

In Brains and Breads we are using Detox library to to write integration test in react native apps. [More info](https://github.com/wix/Detox)

## Integration React Native App with Detox

1. Configure detox for app, you find detail instruction here [Detox documentation](https://github.com/wix/Detox)

2. Write test calling api request in your app.

3. Run Mimic with mock endpoints.

4. Change api address in your app for ex.

```
    detoxTests: {
    apiURL: 'http://172.16.20.15:2002/app-name', -> it's important to set your machine IP address, because fetch doesn't work with localhost
  }
```

5. Run build command -> `detox build --configuration android.emu.release`

6. Run tests command -> `detox test -c android.emu.release`

Good luck :)
