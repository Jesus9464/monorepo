# Setting up the development environment

https://reactnative.dev/docs/environment-setup

# Installation

1. Install NVM see instructions on https://github.com/nvm-sh/nvm
2. Install RVM see instructions on [https://rvm.io](https://rvm.io)
3. Install Nodejs: `nvm install v14.17.5`
   After that you can run `nvm use v14.17.5` and check with `node -v`

4. Install ruby: `rvm install 2.7.4`
   After that you can run `rvm use 2.7.4` and check with `ruby --version`
5. If you do not have yarn installed please run `npm install --global yarn`
6. (Only M1 users) This fix conflicts with node-canvas on Apple M1 - https://github.com/symbol/wallets-lib/issues/6

NOTES:

- (Only M1 users) Make sure that you have insalled NDK 24.0.8215888 version on Android Studio

`brew install pkg-config cairo pango libpng jpeg giflib librsvg`

7. Install node modules: `yarn install`
8. Install bundler: `gem install bundler`
9. Install gem modules: `cd packages/mobile/ios && bundle install`
10. Install pods: `cd ../../ && yarn app pod:install`
11. Add env vars: Copy and paste env files in env folder
12. Add iPhone X simulator if you have Xcode +13:

- Open Xcode: `yarn app xcode`
- Go to Window->Devices and Simulators, select simulators. On the bottom of the left menu select the "+" sign, and then choose the iPhone X simulator on Device Type field then tap create button.

13. `yarn app ios:dev` or `yarn app android:dev` to start development

# Troubleshooting

- If you get error with node_modules and you want to reinstall node modules: `yarn clean:modules && yarn install`
- If you get errors with pods and you want to reinstall pods: `yarn app pod:clean && yarn app pod:install`
- If you get errors with `Command PhaseScriptExecution failed with a nonzero exit code`: run `nvm unalias default`
  More info about the issue above: https://msirius.medium.com/the-resurrection-of-a-year-old-react-native-app-2347de873c0f

- Find development environment issues:

If you have some issue please share run the following command and share with the team:

`yarn app react-native info`

Example:

```sh

System:
    OS: macOS 11.6
    CPU: (8) arm64 Apple M1
    Memory: 170.05 MB / 8.00 GB
    Shell: 5.8 - /bin/zsh
  Binaries:
    Node: 14.17.5 - /var/folders/cx/h7dg5sbd3fb42dgn5ryfxgxh0000gn/T/yarn--1643208875739-0.2974111481238706/node
    Yarn: 1.22.17 - /var/folders/cx/h7dg5sbd3fb42dgn5ryfxgxh0000gn/T/yarn--1643208875739-0.2974111481238706/yarn
    npm: 6.14.14 - ~/.nvm/versions/node/v14.17.5/bin/npm
    Watchman: 2022.01.17.00 - /opt/homebrew/bin/watchman
  Managers:
    CocoaPods: 1.11.2 - /Users/michaelvargas/.rvm/gems/ruby-2.7.4/bin/pod
  SDKs:
    iOS SDK:
      Platforms: DriverKit 21.2, iOS 15.2, macOS 12.1, tvOS 15.2, watchOS 8.3
    Android SDK:
      API Levels: 28, 29, 30, 31
      Build Tools: 29.0.2, 29.0.3, 30.0.2, 31.0.0
      System Images: android-29 | Google APIs ARM 64 v8a, android-31 | Google APIs ARM 64 v8a
      Android NDK: Not Found
  IDEs:
    Android Studio: 2020.3 AI-203.7717.56.2031.7621141
    Xcode: 13.2.1/13C100 - /usr/bin/xcodebuild
  Languages:
    Java: 1.8.0_292 - /usr/bin/javac
  npmPackages:
    @react-native-community/cli: Not Found
    react: Not Found
    react-native: Not Found
    react-native-macos: Not Found
  npmGlobalPackages:
    *react-native*: Not Found
```
