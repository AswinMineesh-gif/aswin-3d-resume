# Aswin Mineesh — 3D Portfolio

## Run locally in VS Code
1. Extract this ZIP to a normal folder (for example `Desktop\Aswin-Portfolio`).
2. Open VS Code → File → Open Folder… → choose the extracted `sen-3d-resume-main` folder.
3. Open **Terminal → New Terminal**.
4. Run:
   ```bash
   cd web
   npm install
   npm run dev
   ```
5. Open the Local URL printed by Vite (usually `http://localhost:5173`).
6. Keep the terminal running. Save a source file and the browser refreshes automatically.
7. To create a production build, run `npm run build` inside the `web` folder.

## Main files to edit
- `web/src/App.tsx`
  - `COPY.en` / `COPY.zh`: hero heading and introduction.
  - `hero-meta`: name, role, portfolio year and location shown around the 3D hero.
- `web/src/ui/Resume.tsx`
  - `RESUME.en` / `RESUME.zh`: education, experience, interests and timeline text.
  - Replace the sample descriptions with your real details. Five entries are currently used to match the five camera focus points in the 3D model.
  - `SOCIAL_LINKS`: add your real social profile links if you want icons to appear.
- `web/src/data/works.ts`
  - `WORKS.en` / `WORKS.zh`: project categories, names, tags and links.
  - Add your own projects; do not claim awards, clients or results you have not earned.
- `web/src/content/works/`
  - Markdown files for expanded project details. Use the existing `example.md` as a template.
- `web/src/styles.css`
  - Colours, typography, spacing, layout and responsive styles.
- `web/public/models/me.glb`
  - The 3D character and its camera animation. Keep the existing file unless you have a replacement GLB compatible with this scene's focus-point naming/animation setup.
- `web/index.html`
  - Browser tab title and search description.
- `web/public/works/covers/`
  - Replace `ad.jpg`, `maker.jpg`, `product.jpg`, `graphics.jpg` with your own section cover images (keep the same filenames), or update `SECTION_COVERS` in `web/src/data/works.ts`.

## Add a project link
In `web/src/data/works.ts`, edit a project item, for example:
```ts
{ name: 'My Project', meta: 'Website', link: 'https://example.com', slug: 'my-project' }
```
Use your real project URL. To add a detailed popup, create `web/src/content/works/my-project.md` following `example.md`.

## Important
- The supplied 3D model and original layout are preserved.
- The five timeline entries should remain five unless you also update `web/src/data/focusPoints.ts` and the matching 3D model focus objects.
- If `npm install` fails, check that Node.js LTS is installed and that your internet connection is working.
