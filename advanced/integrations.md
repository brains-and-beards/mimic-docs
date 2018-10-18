# Integrations

Mimic app is good solution for mobile developers which want to write automatic and integration tests for application. They can do this without any testing database and testing api.

In Brains and Breads we are using Detox library to to write integration test for React Native apps. [Detox library](https://github.com/wix/Detox)

## Integrating React Native Apps with Detox

Detox is an end-to-end testing and automation library for mobile apps. It tests your mobile app while it's running on a real device/simulator, interacting with it just like a real user. We'll show you how you can use it with Mimic to test your API with mocked endpoints.

1. Configure Detox. You will find detailed instructions [here](https://github.com/wix/Detox).

2. Write an E2E test in Detox.

3. Run Mimic with your mocked endpoints.

4. Change your API URL for Detox tests.

```
detoxTests: {
  // It's important to use your machine's IP address, because fetch doesn't work with localhost
  apiURL: 'http://172.16.20.15:2002/app-name'
}
```

5. Run _build_ command -> `detox build --configuration android.emu.release`

6. Run _test_ command -> `detox test -c android.emu.release`

Good luck :)
