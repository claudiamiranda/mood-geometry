# mood geometry

*One object, three moods.*

mood geometry is a small browser tool for distortion as a sculptural, poetic practice. You take a single object and distort it three times, each time toward a different mood. You end with a triptych: three readings of the same thing.

It grew out of an étude from *Cosmic Things*, a Blender and spatial storytelling course: take one modeled object and distort it three ways to express three different moods.

## How it works

- **Five verbs:** melt, swell, wring, smear, erode. Hold a finger or the mouse on the object to apply one. Drag on empty space to rotate the view, and pinch or scroll to zoom.
- **Nothing can be undone.** The only way back is "start over", which resets all three copies and draws new moods.
- **Residue:** each verb leaves its own stain on the surface. Melt leaves a dark, wet umber, swell a flush, wring a bruise, and erode exposes something pale underneath. Smear drags along whatever stain it starts on.
- **Moods** are drawn from a deck. Until you first touch a copy, you can swap its mood or write your own.
- **The record:** each copy keeps a trail of what was done to it (*melted ×4 · eroded*). That trail becomes its caption in the triptych.
- **Light:** tap to move between five setups: *studio* (warm key with a cool rim), *raking* (low, hard side light that brings out texture), *overcast* (soft and even), *candle* (warm glow from below) and *moon* (cool light from above). Each one also changes the soft glow behind the object.
- **Surface:** tap to change what the object is made of: *clay* (the object's own surface), *satin*, *glaze* (a glossy coat, like fired ceramic), *metal*, *wax* (soft, letting a little light through), *glass* (clear, and it takes on the colors around it) and *ghost* (faded and see-through). Scanned textures are kept under every surface.
- **Bring an object:** load any `.glb` file, such as a photogrammetry scan from Kiri Engine or Polycam. The scan's texture is kept.
- **Keep:** save a `.png` of the view, with the moods and records drawn in, or a `.zip` containing the distorted model as `.glb`.

## Running it

It's a single self-contained `index.html` with no build step. three.js and fflate load from jsDelivr.

- **Locally:** run `python3 -m http.server` in this folder and open `http://localhost:8000`. Opening the file directly may also work, but some browsers block module scripts on `file://`.
- **GitHub Pages:** push the repo, then go to Settings → Pages → Deploy from branch → `main` / root. The site will be at `https://<username>.github.io/<repo>/`.

## Changing the deck

The prompts are the `DECK` array near the top of the script in `index.html`. Replace them with your own, in any language. Prompts that describe a situation (*the morning after*, *being called by the wrong name*) tend to produce stranger, more personal shapes than plain emotion words (*sad*, *angry*).

## Notes and limits

- In the exported `.glb`, the stains are stored as vertex colors. The glTF format can only multiply vertex colors with the texture, so dark stains carry over well but pale ones (erode) come out as a faint tint. The `.png` shows the colors exactly as they appear on screen.
- Very dense scans (over about 500k triangles) may feel sluggish on phones. Decimating the scan in Blender first helps.
- Draco-compressed `.glb` files aren't supported. Meshopt-compressed files are.

## Credits

Concept and design: Claudia Miranda ([ghostmeat.xyz](https://ghostmeat.xyz)).
Built with [three.js](https://threejs.org) and [fflate](https://github.com/101arrowz/fflate).
