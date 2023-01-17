## How to Implement TranslateKit into your Shortcut

Last updated June 15, 2019

---

First, make sure you've downloaded [TranslateKit](https://routinehub.co/Shortcut/2691) and added it to your Shortcuts library.

The first step, like with all dependencies, is to check to make sure the user of your Shortcut has TranslateKit added to their library.


<p align=center>
  <img src="/assets/1.jpg" alt="Check for TranslateKit" loading=lazy/>
</p>

First, lets focus on the `Otherwise`. If they don't have TranslateKit, use a `Show Alert` action letting the user know this Shortcut requires TranslateKit and they need to add it to their library.

Use a `URL` action with the `Open URLs` action following it to open translatekit.com where they can download TranslateKit. Allow a cancel button on the alert so the user is not forced to navigate to the URL.

<p align=center>
  <img src="/assets/2.jpg" alt="Prompt to Download TranslateKit" loading=lazy/>
</p>

If they do have TranslateKit, use a `Dictionary` action with your `shortcut_name` and `shortcut_id`. On the first run, this will prompt the user to select a language for your Shortcut. Afterwords, first run or not, `Run Shortcut` will return the language the user has selected, if you'd like to confirm it. Keep in mind it will be returned in the users system language.

![Run TranslateKit](/assets/3.jpg)

<p align=center>
  <img src="/assets/2.jpg" alt="Prompt to Download TranslateKit" loading=lazy/>
</p>

Here is a complete reference of the keys and values you can use in the `Dictionary` action.
* Indicates required key

<table class="dictionary-table">
<thead>
  <tr>
    <th>Key</th>
    <th>Type</th>
    <th>Value</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>shortcut_name <span class="red">*</span></td>
    <td>Text</td>
    <td>Name of your Shortcut</td>
  </tr>
  <tr>
    <td>shortcut_id <span class="red">*</span></td>
    <td>Number</td>
    <td>Your Shortcuts RoutineHub ID</td>
  </tr>
  <tr>
    <td>text</td>
    <td>Text or Dictionary</td>
    <td>Standard text or dictionary to translate</td>
  </tr>
  <tr>
    <td>url</td>
    <td>URL</td>
    <td>iCloud file URL (e.g. your_Shortcut/localization.json). Method for inputting JSON from a url instead of a dictionary value.</td>
  </tr>
  <tr>
    <td>progress</td>
    <td>Boolean</td>
    <td>Whether or not to show an alert before translating letting the user of your Shortcut know that translating your Shortcut may take a moment.</td>
  </tr>
</tbody>
</table>

Then, after the `End If`, place another `Dictionary`, this time with the same keys, but a new key `text`. Set the type as a dictionary.</p>

***NOTE:** Tap on the icon on the previous dictionary and press 'Add to this Shortcut' to duplicate the dictionary in your Shortcut.*

<p align=center>
  <img src="/assets/4.jpg" alt="Run TranslateKit" loading=lazy/>
</p>

You'll notice it says '0 items' in your `Dictionary`, tap on that and a dictionary editor will appear. Enter keys and values to use for menu items, prompts, dialogues, etc.

Tap on the variable. A menu will appear, tap on 'as Text', and select 'Dictionary'. After it, use `Set Variable`, set the name of this as whatever you want, or just name it 'TranslateKit'. This is the variable you will use to access the translated dictionary TranslateKit returns.

<p align=center>
  <img src="/assets/5.jpg" alt="Localization Example" loading=lazy/>
</p>

That's it! You're on your way to integrating TranslateKit into your Shortcut.

### RoutineHub Badge

If you'd like, you can include a "This Shortcut requires TranslateKit" download badge at the bottom of your RoutineHub page. Paste the markdown below at the bottom of your page on RoutineHub.

```markdown
[![Requires TranslateKit](https://i.imgur.com/H8RJgxY.png)](https://routinehub.co/shortcut/2691)
```

## Example

![RoutineHub Badge](https://i.imgur.com/H8RJgxY.png)
