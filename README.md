# AdMob Plus for GDevelop

This is a version of [AdMob Plus](https://admob-plus.github.io/funding.html), a native Cordova plugin, used in [GDevelop game engine](https://gdevelop-app.com) for displaying ads with Google AdMob. It features a clean API built with modern tools.

## About AdMob Plus

If you want to use AdMob plus, it's recommended to first check [the original version](https://admob-plus.github.io/docs/) and [consider funding it](https://admob-plus.github.io/funding).

Most changes or fixes done in this version should be contributed back to the original project.

## Usage

If you want to integrate ads in your GDevelop game, check [GDevelop documentation about AdMob](http://wiki.compilgames.net/doku.php/gdevelop5/all-features/admob).

If you want to use this plugin in your Cordova app:

```sh
cordova plugin add gdevelop-cordova-admob-plus --variable APP_ID_ANDROID=ca-app-pub-xxx~xxx --variable APP_ID_IOS=ca-app-pub-xxx~xxx
```

Then follow the [original plugin documentation](https://admob-plus.github.io/docs/).

## Contributing

Be sure to [yarn](https://yarnpkg.com/) installed and install the dependencies:

```sh
yarn
```

On macOS, install additional tools with Homebrew:

```sh
brew install swiftlint
brew install ios-deploy
```

### Working on the plugin (Cordova)

Prepare the Cordova plugin:

```
cd packages/cordova
yarn prepare
```

In a Cordova project, after `cordova platform add [ios|android]` you can add the local plugin:

```
cordova plugin add --link path/to/admob-plus/packages/cordova/ --variable APP_ID_IOS=ca-app-pub-3940256099942544~3347511713 APP_ID_ANDROID=ca-app-pub-3940256099942544~3347511713
```

Run `cordova plugin rm cordova-admob-plus` beforehand in case of problem.

### Tests and commits

Run linting and tests:

```
yarn test-ios:lint
yarn lint
yarn test
```

You can run the test app:

```
cd examples/basic
cordova platform add android && cordova run android
cordova platform add ios && cordova run ios
```

Commit as usual with git. Hooks will run linting and commitlint (so you must have run `yarn` before).

### Publish the plugin (Cordova)

Ensure you are logged in npm (`npm login`) and have the rights to publish the npm package.

```
cd packages/cordova
npm publish
```

## License and Disclaimer

This project is not officially affiliated with Google.

This project is [MIT licensed](./LICENSE).
