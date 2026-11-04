# ivCAMPUS languages

All the ivCAMPUS text that needs translating, in one place. This repository is where translations are collected.

Nothing here runs. A translation reaches the product only after a developer copies it into the repository that owns it.

## What's here

| Folder | What users see | Copied from | Commit | Commit date |
|---|---|---|---|---|
| `client/` | The main ivCAMPUS app | `campus-alpha-client` (`master`), `src/kits/language/` | `358f9fa1a6` | 2026-10-27 |
| `emails/` | Sign-up, sign-in, onboarding and invitation emails | `identity-provider` (`main`), `preferred_languages/` | `6c6b50cdd6` | 2026-10-27 |
| `campus-rooms/` | Default rooms in a new campus | `campus-api` (`mongodb/main`), `src/handler/controller/campus/` | `7bc8390e96` | 2026-09-15 |
| `open-doors/` | Access passes for visitors | `campus-open-doors-management` (`main`), `lib/` | `97b05c8b70` | 2026-05-12 |

Files are exact copies, so they keep their original format. English and German are the reference languages.

## How to add a language

French is used as the example here.

1. Create a branch, such as `add-french`.
2. Add the language in each folder:

   | Folder | What to do |
   |---|---|
   | `client/` | Copy `en.ts` to `fr.ts`, change `export const en` to `export const fr`, then translate |
   | `emails/` | Copy `english.json` to `french.json`, then translate |
   | `campus-rooms/` | In `campus.translation.ts`, copy the whole `en: { ... }` block, name it `fr: { ... }`, put it after `de`, then translate |
   | `open-doors/` | In `translations.ts`, copy the whole `en: { ... }` block, name it `fr: { ... }`, put it after `de`, then translate |

3. Open a pull request. Merging it means the translation is finished and ready to be collected.

## Rules for translating

- **Translate only the text in quotes.** Don't change key names, the text to the left of the colon.
- **Keep placeholders exactly as they are,** such as `{memberCount}`. You can move them within a sentence.
- **Keep spaces at the start and end of text.** Some text is joined to other text, such as `"Sie werden zum Campus von "`.
- **Leave links as they are** unless you know a version exists in your language.
- **Don't edit the English or German text here.** It's overwritten at the next refresh. If you find a mistake, tell a developer so it can be fixed in the app.
- **Don't edit `client/stringsType.ts`.** It's the list of keys that the app expects.

## What's missing

- Text written directly in the application code instead of in language files. It will be added here after it has been moved into those files.
- Text from features not yet merged into the default branches, such as `campus-alpha-client` pull request 875.
- The OX plugin. Its language files contain only sample text from a template, and its few real strings are written directly in the code.
