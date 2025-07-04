# The Echo Tape

**The Echo Tape** is an experimental interactive story told entirely in the browser. Every episode plays out like a choose‑your‑own‑adventure, letting you guide the characters down branching paths. The project started as a fun way for two friends to learn and tell a weird story together.

Episode 1 ultimately aims for about an hour of play time, but the project is still in its infancy—less than ten percent of the planned content exists so far.

Episode 1 is playable and features sound effects and a scene history overlay. Progress is saved in your browser using local or session storage. You can export this data from the Dev Tools screen and import it on another device. A new **Enable Sync** button lets you choose a file for automatic backups. If the file already contains a save, it's loaded immediately – store it in a synced folder to keep progress across devices. Episode 2 is under construction.

## Writing Episodes

All episode data resides in the `episodes` folder. Each file is a JSON document describing a list of scenes. Writers can follow the structure documented in [WRITING_GUIDE.md](WRITING_GUIDE.md) and [EPISODE_SCHEMA.md](EPISODE_SCHEMA.md) to create new episodes. A simple CLI lives in `episode-builder/` for interactively generating these JSON files. After editing a `.json` file, run `npm run build-episodes` to regenerate the embedded `.js`, update `sw.js` with the correct cache list, and commit both files.
For a broader sense of tone and structure, see [SCRIPT_GUIDELINES.md](SCRIPT_GUIDELINES.md), which contains an example script and style notes. A full draft of Act&nbsp;1 lives in [ACT1_DRAFT.md](ACT1_DRAFT.md).
Image assets are stored in the `images` folder. Sound effects and music live in the `audio` folder.

## Getting Started

1. Install **Node.js 18** or higher.
2. Clone or download this repository.
3. **Do not open `index.html` directly.** Serve the folder with a simple HTTP server. `npm start` runs a built-in static server, or you can use `npx http-server`. Episode data is embedded so it works offline once loaded.
4. Run `npm install` (if needed) and `npm test` to verify required files and script syntax.
5. Run `npm run lint` to check code style and catch common mistakes.
6. After editing an episode's `.json`, run `npm run build-episodes` to regenerate the `.js` files and update `sw.js`, then run `npm test` to catch any issues.
7. The build script now computes a fingerprint of all assets and embeds it in `sw.js` to automatically invalidate old caches when files change.
8. Use the **Dev Tools** button on the title screen if you need to clear saved progress.

## Audio Controls

Use the sliders in the lower corner to adjust volume. Music and sound effects have separate levels. A new **Voice Volume** slider controls playback volume for voiceover clips.

## Versioning

The project uses simple incremental build numbers in the form
`MAJOR.MODERATE.MINOR.HOTFIX`. Only the last digit increases for each
release. See [VERSIONING.md](VERSIONING.md) for more details.
## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for workflow tips and example commands.


## License

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License**. See the [LICENSE](LICENSE) file for details.

