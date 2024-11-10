# Translation Guide

## Preparing the Setup

1. Clone this repository with all submodules:
```sh
git clone --recursive https://github.com/vrtmrz/obsidian-livesync
```
2. Create the `ls-debug` folder in your vault's `.obsidian` directory (e.g., `.../dev/.obsidian/ls-debug`).

## Adding Translations for Existing Terms

1. Install dependencies and build the plugin in development mode:
```sh
cd obsidian-livesync
npm i -D
npm run buildDev
```
2. Copy the `main.js` file to your vault's `.obsidian/plugins/obsidian-livesync` folder, then run Obsidian-Self-hosted LiveSync.
3. A `missing-translation-yyyy-mm-dd.jsonl` file will be generated, please fill in the translations for the missing terms.
4. Rebuild the plugin and check if the translations are displayed correctly.
5. Merge your changes into `rosetta.ts` and submit a PR to [livesync-commonlib](https://github.com/vrtmrz/livesync-commonlib).

## Marking Messages for Translation

1. Find the message to translate in the code.
2. Convert the literal message to a tagged template literal using `$f`:
```diff
- Logger("Could not determine passphrase to save data.json! Please check your configuration.", LOG_LEVEL_URGENT);
+ Logger($f`Could not determine passphrase to save data.json! Please check your configuration.`, LOG_LEVEL_URGENT);
```
3. Submit a PR to [obsidian-livesync](https://github.com/vrtmrz/obsidian-livesync).
4. Follow the steps of "Add Translations for Existing Terms" to add translations for the new message.