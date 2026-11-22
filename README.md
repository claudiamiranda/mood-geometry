# mood geometry

*One object, three moods.*

mood geometry is a small browser app for distortion as a sculptural, poetic practice. You're dealt three moods, and for each one you take a simple form and push it until it answers. You end with three *mood forms*, side by side as a triptych: three readings of a feeling, in clay, glass or metal.

It grew out of an étude from *Cosmic Things*, a Blender and spatial storytelling course taught by Claudia Miranda at Gray Area in 2026: take one modeled object and distort it three ways to express three different moods.

Live at **mood.ghostmeat.xyz**.

## How it goes

0. **A frame.** A short opening text, *a feeling has a shape before it has a name*, with links to "about this project" and, once you've kept something, "your shelf".
1. **Deal.** Three mood cards are shuffled and dealt by chance. Tap a card to redraw it, deal all three again, or write your own (up to 40 characters each).
2. **Shape.** For each mood, choose a starting form (block, sphere, column or shard, or bring your own `.glb`), then shape it with five verbs: melt, swell, wring, smear, erode. Hold on the object to apply one; drag on empty space to turn the view; pinch or scroll to come closer. Nothing can be undone. Each verb leaves its own stain, and each piece keeps a record of what was done to it (*melted ×4 · eroded*), which becomes its caption.
3. **Shape and surface.** A switch above the bottom bar moves between shaping and choosing the surface: clay, glaze, metal, glass or ghost. Each mood remembers how you were looking at it.
4. **All three.** "see all three" appears once every mood has a form. Choose the one light they share: soft, studio or low.
5. **Keep.** Save the triptych image, each mood form as its own image, the models (`.glb` in a zip), see the three in AR on a phone, or add the set to your shelf.
6. **Your shelf.** Sets you keep here can be opened again from the start screen, re-lit, viewed in AR and saved again. They can't be changed, only removed.

Tap the wordmark at any time to start over. Once there's work to lose, it asks first.

## Sound

Off until you tap the speaker in the top corner. Everything is synthesized live with the Web Audio API; there are no audio files. Each light has its own room tone, each verb follows the speed of your drag, each surface has a short strike, and the deal, beginning, next mood and see all three have quiet cues. Buttons are silent. On a phone it follows the silent switch.

## Saving, privacy and counts

- Everything you make stays in your browser (IndexedDB): the set in progress and your shelf. Nothing is uploaded. It doesn't follow you to another device, and Safari may clear it after a week without a visit, so save the files of anything you want to keep.
- Visits and a few steps (dealing, beginning, seeing all three, each kind of keep, opening AR) are counted with [GoatCounter](https://www.goatcounter.com), which uses no cookies and collects no personal data. The moods and the shapes are never sent. Counting only runs on the published site.

## AR

On phones, "see it in AR" hands the three pieces to the phone's own viewer through [`<model-viewer>`](https://modelviewer.dev): Quick Look on iPhone and iPad, Chrome's WebXR mode on Android. They start at about 15 cm each, side by side, and can be pinched to any size. Glass becomes standard clear glass and ghost a plain see-through material; the app's light choice doesn't apply, since AR uses the light in the room.

## Running it

It's a single self-contained `index.html` with no build step. three.js, fflate and model-viewer load from jsDelivr.

- **Locally:** run `python3 -m http.server` in this folder and open `http://localhost:8000`. Some browsers block module scripts on `file://`.
- **GitHub Pages:** Settings → Pages → Deploy from branch → `main` / root.

## Changing the deck

The prompts are the `DECK` array near the top of the script in `index.html`. Prompts that describe a situation (*the morning after*, *being called by the wrong name*) tend to produce stranger, more personal shapes than plain emotion words (*sad*, *angry*).

## Files

- `index.html`: the app.
- `brand/`: the wordmark (dark, light, small and on a plate) as outlined SVG and PNG, and the icon and favicons.
- `open/`: the earlier, open-ended version (one object, three moods, no steps), kept for reference and not linked from the app. It's also preserved on the `v1` branch.
- `guided/`: forwards to the main address, so older links keep working.

## Notes and limits

- In the exported `.glb`, stains are stored as vertex colors, which glTF multiplies with the texture: dark stains carry over well, pale ones (erode) come out as a faint tint. The images show colors exactly as on screen.
- Very dense scans (over about 500k triangles) may feel sluggish on phones. Decimating the scan in Blender first helps.
- Draco-compressed `.glb` files aren't supported. Meshopt-compressed files are.

## Credits

Concept and design: Claudia Miranda ([ghostmeat.xyz](https://ghostmeat.xyz)).
Built with [three.js](https://threejs.org), [fflate](https://github.com/101arrowz/fflate) and [model-viewer](https://modelviewer.dev).

## License

© 2026 Claudia Miranda. All rights reserved. The source is here to look at and learn from by reading, not to reuse. Please ask before copying, adapting or hosting any part of it: [ghostmeat.xyz](https://ghostmeat.xyz). See [LICENSE](LICENSE).
