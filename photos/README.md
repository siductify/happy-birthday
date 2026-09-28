# 📸 the pics

Every image file dropped in this folder shows up on the birthday site, automatically.

## Adding photos

1. Copy your images in here (`.jpg`, `.jpeg`, `.png`, `.webp`, `.gif`, `.avif`).
2. Want a caption under a photo? Name the file like this:

   ```
   2019__the day we got lost in Mangalore.jpg
   ```

   Everything after `__` becomes the handwritten caption.
   No `__`? No caption — it still looks cute.

3. Rebuild the list the site reads:

   ```bash
   python3 photos/build-manifest.py
   ```

4. Refresh the page. That's it.

Photos are shown in filename order, so prefix them with numbers
(`01-...`, `02-...`) if you care about the order. Anything named
`placeholder-*` gets pushed to the end, so your real pics always lead.
