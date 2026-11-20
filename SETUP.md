# Setup — ZacGeo animated GitHub profile

1. Download the project ZIP and extract it.
2. Open your **existing** public profile repository: https://github.com/ZacGeo/ZacGeo . **Do not create a second repository.**
3. Upload `README.md`, `assets/`, `scripts/` and `.github/workflows/` to the **main** branch. Hidden `.github` folders must keep their directory structure. Using a local Git clone or VS Code makes this easiest.
4. Go to **Settings → Actions → General → Workflow permissions**. Enable **Read and write permissions** if GitHub permits it. The workflow also sets `permissions: contents: write` explicitly.
5. Under **Actions**, manually run **Update profile stats and 3D contributions**. This fetches your current public GitHub stats and creates `profile-3d-contrib/profile-green-animate.svg` on `main`. The first update also replaces the stats placeholder SVG.
6. Return to https://github.com/ZacGeo and refresh. The 3D skyline cannot render until its first successful workflow run.

## Customizing

- `assets/hero.svg`: edit displayed name, tagline and labels.
- `assets/projects.svg`: edit project names/descriptions. The four cards correspond to the linked source repositories in README.md.
- `README.md`: customize about-me and project table. The four project links are already filled in.
- `scripts/generate_stats.py`: uses public GitHub REST API. It counts **public repositories**, stars on owned non-fork public repos, and followers. It deliberately does not claim an annual contribution total.
- The contribution skyline reflects GitHub's attribution of contributions. Missing commits in your contribution calendar should be fixed by checking account email, default branch and private contribution display.

## Requirements & troubleshooting

- Profile repo must be `ZacGeo/ZacGeo` and public.
- SVG files animate as external `<img>` references; inline JavaScript is not required.
- Third-party services (typing SVG, Skill Icons, 3D generator) can experience downtime, GitHub Actions permissions issues or rate limits.
- If the skyline image is broken, run the stats/3D workflow and check the generated directory on `main`.
- If the image URLs are cached by GitHub, wait for refresh; do not invent statistics.

## Credits

- 3D contributions: https://github.com/yoshi389111/github-profile-3d-contrib
- Typing: https://github.com/DenverCoder1/readme-typing-svg
- Icons: https://github.com/tandpfun/skill-icons

Inspired by the dark teal GitSkins-style reference provided by the user. Original custom SVG hero, project panel and statistics card; no GitSkins proprietary template files are bundled.
