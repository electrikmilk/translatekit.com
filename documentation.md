## How to Implement TranslateKit into your Shortcut

Last updated June 15, 2019

---

First, make sure you've downloaded [TranslateKit](https://routinehub.co/Shortcut/2691) and added it to your Shortcuts library.

The first step, like with all dependencies, is to check to make sure the user of your Shortcut has TranslateKit added to their library.

![Check for TranslateKit](/assets/1.jpg)

First, lets focus on the `Otherwise`. If they don't have TranslateKit, use a `Show Alert` action letting the user know this Shortcut requires TranslateKit and they need to add it to their library.

Use a `URL` action with the `Open URLs` action following it to open translatekit.com where they can download TranslateKit. Allow a cancel button on the alert so the user is not forced to navigate to the URL.

![Prompt to Download TranslateKit](/assets/2.jpg)

If they do have TranslateKit, use a `Dictionary` action with your `shortcut_name` and `shortcut_id`. On the first run, this will prompt the user to select a language for your Shortcut. Afterwords, first run or not, `Run Shortcut` will return the language the user has selected, if you'd like to confirm it. Keep in mind it will be returned in the users system language.

![Run TranslateKit](/assets/3.jpg)

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

<p>Then, after the <span class="action-ref">End If</span>, place another <span class="action-ref">Dictionary</span>, this time with the same keys, but a new key 'text'. Set the type as a dictionary.</p>
<p><b>PROTIP:</b> Tap on the icon on the previous dictionary and press 'Add to this Shortcut' to duplicate the dictionary in your Shortcut.</p>

![Run TranslateKit](/assets/4.jpg)

<p>You'll notice it says '0 items' in your <span class="action-ref">Dictionary</span>, tap on that and a dictionary editor will appear. Enter keys and values to use for menu items, prompts, dialogues, etc.</p>
<p>Tap on the variable. A menu will appear, tap on 'as Text', and select 'Dictionary'. After it, use <span class="action-ref">Set Variable</span>, set the name of this as whatever you want, or just name it 'TranslateKit'. This is the variable you will use to access the translated dictionary TranslateKit returns.</p>


![Localization Example](/assets/5.jpg)

That's it! You're on your way to integrating TranslateKit into your Shortcut.
