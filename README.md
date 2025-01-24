# DNSCloak for iOS

_iOS GUI and wrapper for [dnscrypt-proxy 2](https://github.com/jedisct1/dnscrypt-proxy)._

Uses [Apache Cordova](https://cordova.apache.org) as app platform & [Framework7](https://framework7.io) as UI.

Available on the [App Store](https://itunes.apple.com/app/id1452162351).

Master Branch
----------------

This branch works with Xcode 10.0 and supports iOS 10.0+.

Build Instructions for Master
------------------

1. Install the latest [Xcode developer tools](https://developer.apple.com/xcode/downloads/) from Apple.

1a. Install python2
    ```shell
    brew install pyenv
    # tune compilation
    env PYTHON_CONFIGURE_OPTS='--enable-optimizations --with-lto' PYTHON_CFLAGS='-march=native -mtune=native' pyenv install --verbose 3.13.1
    env PYTHON_CONFIGURE_OPTS='--enable-optimizations --with-lto' PYTHON_CFLAGS='-march=native -mtune=native' pyenv install --verbose 2.7.18
    pyenv global 3.13.1 2.7.18
    ```
2. Install [Node.js & npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).
    ```shell
    brew install node@20
    ```
3. Install [golang](https://golang.org/doc/install). 1.12+ is required for TLS 1.3 support.
4. Clone the repository:

  ```shell
  git clone https://github.com/s-s/dnscloak.git
  ```

5. Pull in the project dependencies:

  ```shell
  cd dnscloak
  npm install && npm install --only=dev
  ```

6. Build framework, (re)build www folder for cordova and prepare project for Xcode:

  ```shell
  npm run build
  ```

7. Open `platforms/ios/DNSCryptApp.xcworkspace` in Xcode.
8. Build the `DNSCryptApp` scheme.
