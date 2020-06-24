# FFmpeg iOS build script

This is a shell script to build FFmpeg libraries for iOS and tvOS apps. It is copied from https://github.com/kewlbear/FFmpeg-iOS-build-script

We currently only require the arm64 variant of the libs, so lipo packaging is not needed. The built libraries can be found in the 'thin' folder in this directory.

Tested with:

* 8i FFmpeg 4.2.3.1
* Xcode 11.5

## Requirements

* https://github.com/libav/gas-preprocessor
* yasm 1.2.0

## Usage

Use build-ffmpeg-tvos.sh for tvOS.

* To build everything:

        ./build-ffmpeg.sh

* To build arm64 libraries:

        ./build-ffmpeg.sh arm64

* To build fat libraries for armv7 and x86_64 (64-bit simulator):

        ./build-ffmpeg.sh armv7 x86_64

* To build fat libraries from separately built thin libraries:

        ./build-ffmpeg.sh lipo

## External libraries

You should link your app with

* libz.dylib
* libbz2.dylib
* libiconv.dylib
