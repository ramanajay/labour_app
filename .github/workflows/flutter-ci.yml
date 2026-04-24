name: Flutter CI

on:
push:
branches: [ "main" ]
pull_request:

jobs:
build:
runs-on: ubuntu-latest

steps:
- name: Checkout Code
uses: actions/checkout@v3

- name: Install Flutter
uses: subosito/flutter-action@v2
with:
flutter-version: "3.22.0"

- name: Get Dependencies
run: flutter pub get

- name: Analyze Code
run: flutter analyze

- name: Run Tests
run: flutter test

- name: Build APK
run: flutter build apk --release

- name: Upload APK
uses: actions/upload-artifact@v3
with:
name: app-release
path: build/app/outputs/flutter-apk/app-release.apk