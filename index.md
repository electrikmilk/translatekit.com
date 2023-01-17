## What is TranslateKit?

### [Download on RoutineHub](https://routinehub.co/shortcut/2691)

TranslateKit is an [iOS Shortcut](https://support.apple.com/guide/shortcuts/welcome/ios) that brings multilingual support to other Shortcuts via translation APIs built into the Shortcuts app.

Implementation into your Shortcut is simple, all translation, localization, and caching is all handled by TranslateKit.

It's a fast and lightweight. After first translating your shortcut on a users device, it's just as fast as any other localization. The difference is, you don't have to translate your shortcut, TranslateKit takes care of it all for you!

To learn more about how to implement TranslateKit into your shortcut, see the [documentation](documentation.md).

## How does it work?

TranslateKit recieves a dictionary from your shortcut that it uses to identify your shortcut when storing and accessing translations for it.

It also recieves the text, dictionary, or JSON file you'd like it to translate. It goes through each key and translates the value. It re-creates the dictionary given to it and returns it with the same keys, but translated values.
