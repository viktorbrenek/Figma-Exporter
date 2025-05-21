# Figma Auto Icon Exporter

**Figma Auto Icon Exporter** is a simple Figma plugin that automates icon cleanup and preparation for SVG export. It detaches instances, removes unnecessary layers, groups content, and allows quick selection of icons by style (`regular` or `bold`).

---

## 🧩 Expected Figma File Structure

For the plugin to work correctly, your Figma file should follow this structure:

```
Page
├── Frame: regular - these are parents 
│   ├── Frame: communication - whatever name - these are categories
│   │   ├── Frame: icon-name-1 - these are icon names
│   │   ├── Frame: icon-name-2
│   │   └── ...
│   └── Frame: ui
│       ├── Frame: icon-name-3
│       └── ...
├── Frame: bold
│   ├── Frame: web
│   │   ├── Frame: icon-name-4
│   │   └── ...
│   └── ...
```

- Each style (`regular`, `bold`) must be a top-level `FRAME` on the page.
- Each style contains categories (`communication`, `ui`, `web`...), also `FRAME`s.
- Inside each category are individual icons – each icon is a `FRAME`.
- Icons are expected to be sized `24x24 px`.

---

## 🚀 How to Use

1. Open your prepared Figma file.
2. Launch the `Figma Auto Icon Exporter` plugin.
3. Click the **Start** button to perform:
   - Detaching all instances
   - Removing unnecessary groups and “color” layers
   - Unmasking layers
   - Applying black fill to all elements
   - Wrapping icon content in a `__content` group inside each icon frame
4. Click **Select Regular** or **Select Bold**
   - This selects all icon frames under the specified style (`regular` or `bold`)
   - Automatically sets `exportSettings` to `SVG` for each
5. Open the Figma Export dialog (`Ctrl + Shift + E` or **File → Export**)
   - All selected icons are ready for batch export

---

## 💡 Notes

- Figma does **not allow automatic saving or triggering of the export dialog** via plugin API.
- This plugin prepares everything, and you finish the export manually in one click.
- All icons will be exported as clean, flat SVG files.

---

## 📄 License

MIT – use freely, modify, contribute.