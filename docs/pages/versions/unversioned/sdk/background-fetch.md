---
title: BackgroundFetch
sourceCodeUrl: 'https://github.com/expo/expo/tree/master/packages/expo-background-fetch'
---

import APISection from '~/components/plugins/APISection';
import PlatformsSection from '~/components/plugins/PlatformsSection';

**`expo-background-fetch`** provides an API to perform [background fetch](https://developer.apple.com/documentation/uikit/core_app/managing_your_app_s_life_cycle/preparing_your_app_to_run_in_the_background/updating_your_app_with_background_app_refresh) tasks, allowing you to run specific code periodically in the background to update your app. This module uses [TaskManager](task-manager.md) Native API under the hood.

<PlatformsSection android emulator ios simulator />

## Known issues

BackgroundFetch only works when the app is backgrounded, not if the app was terminated or upon device reboot. [Here is the relevant Github issue](https://github.com/expo/expo/issues/3582)

## Installation

For [managed](../../../introduction/managed-vs-bare.md#managed-workflow) apps, you'll need to run `expo install expo-background-fetch`. To use it in [bare](../../../introduction/managed-vs-bare.md#bare-workflow) React Native app, follow its [installation instructions](https://github.com/expo/expo/tree/master/packages/expo-background-fetch);

## Configuration

In order to use `BackgroundFetch` API in standalone, detached and bare apps on iOS, your app has to include background mode in the `Info.plist` file. See [background tasks configuration guide](task-manager.md#configuration-for-standalone-apps) for more details.

On Android, this module might listen when the device is starting up. It's necessary to continue working on tasks started with `startOnBoot`. It also keeps devices "awake" that are going idle and asleep fast, to improve reliability of the tasks. Because of this both the `RECEIVE_BOOT_COMPLETED` and `WAKE_LOCK` permissions are added automatically.

## API

```js
import * as BackgroundFetch from 'expo-background-fetch';
```

<APISection packageName="expo-background-fetch" apiName="BackgroundFetch" />