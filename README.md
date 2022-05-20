# define ANDROID_HOME variable
```shell
$ vim .bashrc
export ANDROID_HOME=$HOME/android-sdk-linux
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools

# make ANDROID_HOME folder
$ mkdir $ANDROID_HOME
```

# download command-tools from android developer and extract and rename it to $ANDROID_HOME/cmdline-tools/latest 
find the latest command tools at https://developer.android.com/studio#command-tools
like:
```shell
$mkdir -p $ANDROID_HOME/cmdline-tools
$cd $ANDROID_HOME/cmdline-tools
$wget -c https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip
--2022-05-20 11:47:25--  https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip
Resolving dl.google.com (dl.google.com)... 114.250.70.33
Connecting to dl.google.com (dl.google.com)|114.250.70.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 114168525 (109M) [application/zip]
Saving to: 'commandlinetools-linux-8512546_latest.zip'

commandlinetools-linux-8512546_latest.zi 100%[===============================================================================>] 108.88M  7.76MB/s    in 16s

2022-05-20 11:47:49 (6.92 MB/s) - 'commandlinetools-linux-8512546_latest.zip' saved [114168525/114168525]

$unzip commandlinetools-linux-8512546_latest.zip

$mv cmdline-tools latest

```

# list all installed and available packages are printed ou
$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https --list

# install cmake
```shell
$ $ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --install "cmake;3.10.2.4988404"
```

# install build tools
$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --install "build-tools;29.0.0"

# install ndk-bundle
$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --install "ndk-bundle"

#install ndk

$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --install "ndk;24.0.8215888"
# install platform tools

$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --install "platforms;android-29"
$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --install "platform-tools"

# show installed
$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager --no_https  --list_installed
Installed packages:=====================] 100% Fetch remote repository...
  Path                 | Version      | Description                     | Location
  -------              | -------      | -------                         | -------
  build-tools;29.0.0   | 29.0.0       | Android SDK Build-Tools 29      | build-tools/29.0.0
  cmake;3.10.2.4988404 | 3.10.2       | CMake 3.10.2.4988404            | cmake/3.10.2.4988404
  emulator             | 31.2.10      | Android Emulator                | emulator
  ndk-bundle           | 22.1.7171670 | NDK                             | ndk-bundle
  ndk;24.0.8215888     | 24.0.8215888 | NDK (Side by side) 24.0.8215888 | ndk/24.0.8215888
  patcher;v4           | 1            | SDK Patch Applier v4            | patcher/v4
  platform-tools       | 33.0.1       | Android SDK Platform-Tools      | platform-tools
  platforms;android-29 | 5            | Android SDK Platform 29         | platforms/android-29
