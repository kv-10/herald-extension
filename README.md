# petvalu-bot

Firefox extension for Pet Valu portal order automation.

## Files
- `petvalu-bot.xpi` — the extension (installable)
- `update.xml` — Firefox auto-update manifest

## Pushing an update

1. Make your changes to the extension source
2. Zip the extension folder and rename it to `petvalu-bot.xpi`
3. Update the version number in both:
   - `update.xml` → `<version>X.X</version>`
   - The source `manifest.json` → `"version": "X.X"`
4. Commit and push — parents get it on next manual check (`about:addons` → gear → Check for Updates)

## First install (parents)
1. Download `petvalu-bot.xpi` from this repo
2. Open Firefox Developer Edition → `about:addons`
3. Gear icon → Install Add-on From File → select `petvalu-bot.xpi`
