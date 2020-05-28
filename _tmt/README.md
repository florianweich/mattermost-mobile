# TMT Mattermost App

## Build Preparations

1. Meet the prerequisites from [Developer Setup](https://developers.mattermost.com/contribute/mobile/developer-setup/) and [Build Preparations](https://developers.mattermost.com/contribute/mobile/build-your-own/preparation/).

2. Git clone this repo.

3. Make sure the CocoaPods repo is up-to-date: `pod repo update`

4. Run `make pre-run` to install all dependencies.

5. You can test run the app with `make run` in the iOS simulator and see if installation worked.

## TMT Style and Signing

1. Checkout the desired version (by tag):

   ```sh
   git checkout $tag -b tmt-release
   ```

2. Copy TMT icon assets to the build override directory:

   ```sh
   mkdir -p ./assets/override/release && \
   cp -R ./assets/base/release/* ./assets/override/release/ && \
   cp ./_tmt/AppIcon/ios/* ./assets/override/release/icons/ios
   ```

3. Copy config.json (contains predefined Mattermost server configurations for the app):

   ```sh
   cp ./_tmt/config.json ./assets/override
   ```

4. Create local fastlane .env file:

   ```sh
   cp ./_tmt/fastlane/.env.example ./fastlane/.env
   ```

5. Download Provisioning Profiles within Xcode (make sure to use the correct Apple Developer Account) to have them ready for use.
