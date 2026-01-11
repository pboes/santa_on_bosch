# Santa on Bosch – Audio Player with NFC Tags

A simple Jekyll-based static website for playing audio files via NFC tags. Perfect for interactive art installations, museum exhibits, educational projects, or any scenario where you want physical objects (NFC tags) to trigger audio playback on a smartphone.

## 🎯 What This Project Does

This project creates a simple website where:
- Each audio track gets its own webpage with a custom audio player
- Users can tap NFC tags with their smartphones to open specific track pages
- The pages work on any device (iPhone, Android, desktop) without installing apps
- All pages share a beautiful, consistent design with a background image

## 🏗️ Project Structure

```
.
├── _config.yml           # Jekyll configuration
├── _layouts/
│   └── track.html       # Template for all audio track pages
├── assets/
│   ├── audio/           # Your .m4a audio files go here
│   └── background.png   # Background image for all pages
├── tracks/              # One .md file per audio track
│   ├── t01.md
│   ├── t02.md
│   └── ...
└── index.html           # Main page with links to all tracks
```

## 🚀 How to Set This Up for Your Own Project

### Step 1: Fork This Repository

1. Click the "Fork" button at the top of this GitHub repository
2. This creates your own copy of the project

### Step 2: Enable GitHub Pages

1. Go to your forked repository on GitHub
2. Click **Settings** → **Pages** (in the left sidebar)
3. Under "Source", select **Deploy from a branch**
4. Select **main** branch and **/ (root)** folder
5. Click **Save**
6. Your site will be published at: `https://[your-username].github.io/[repository-name]/`

### Step 3: Add Your Audio Files

1. In your repository, navigate to `assets/audio/`
2. Click **Add file** → **Upload files**
3. Upload your audio files (`.m4a` format works best for web)
4. Commit the changes

**Tip:** Keep filenames simple and descriptive (e.g., `track-01-intro.m4a`, `story-chapter-1.m4a`)

### Step 4: Create Track Configuration Files

For each audio file, you need a corresponding `.md` file in the `tracks/` folder.

**Option A: Manually create files**

1. Go to the `tracks/` folder
2. Click **Add file** → **Create new file**
3. Name it `t01.md` (or `t02.md`, `t03.md`, etc.)
4. Add this content:

```yaml
---
layout: track
title: "Your Track Title Here"
audio: /assets/audio/your-audio-file.m4a
---
```

5. Commit the file
6. Repeat for each audio file

**Option B: Use AI assistance**

You can ask an AI assistant (like ChatGPT, Claude, or GitHub Copilot) to help:

*"I have 10 audio files in my assets/audio/ folder named [list your files]. Please create the corresponding .md config files in the tracks/ folder, numbered t01.md through t10.md, with descriptive titles based on the filenames."*

### Step 5: Customize the Design

#### Change the Background Image

1. Replace `assets/background.png` with your own image
2. For best results, use a high-resolution image (1920x1080 or larger)

#### Adjust Transparency

To make the card overlay more/less transparent:

1. Edit `_layouts/track.html` and `index.html`
2. Find this line in the `.card` style section:
   ```css
   background: rgba(255,255,255,0.72);
   ```
3. Change `0.72` to a different value:
   - `0.9` = more opaque (less transparent)
   - `0.5` = medium transparency
   - `0.3` = very transparent

#### Change Colors and Styling

Ask an AI assistant to help customize the CSS in `_layouts/track.html` and `index.html`. For example:

*"Can you change the card styling in track.html to use a dark theme with blue accents?"*

### Step 6: Set Up Your NFC Tags

#### What You Need

- **NFC tags** (NTAG215 or NTAG216 work well, available on Amazon/eBay)
- **NFC writing app** on your smartphone:
  - iPhone: "NFC Tools" (free) or "Shortcuts" app (built-in)
  - Android: "NFC Tools" (free) or "Trigger" (free)

#### Programming the Tags

1. **Get your track URLs**: After GitHub Pages is set up, your tracks will be at:
   ```
   https://[your-username].github.io/[repo-name]/tracks/t01/
   https://[your-username].github.io/[repo-name]/tracks/t02/
   ```

2. **Write to NFC tag**:
   - Open your NFC writing app
   - Select "Write" → "Add a record" → "URL/URI"
   - Paste the track URL
   - Tap "Write" and hold your NFC tag to the phone
   - Label the physical tag (e.g., with a sticker showing "Track 01")

3. **Test it**: Lock your phone and tap the NFC tag - it should open the track page directly!

#### Tips for NFC Tags

- **Protect tags from damage**: Consider using weatherproof or encased NFC tags
- **Tag placement**: Works best when placed on non-metallic surfaces
- **Read range**: Users need to hold phone within 1-2 inches of the tag
- **Lock your tags** (optional): Once programmed, you can lock tags to prevent accidental overwrites

### Step 7: Test Everything

1. Visit your GitHub Pages URL
2. Check that the index page shows all tracks
3. Click on each track to verify audio plays correctly
4. Test with NFC tags on both iPhone and Android if possible

## 🎨 Customization Ideas

### For Teachers/Educational Use

- **Student Poetry Project**: Each student records a poem, gets their own track page and NFC tag
- **Audio Museum**: Create exhibits where objects have NFC tags that play explanations
- **Language Learning**: Practice pronunciation with audio examples
- **Storytelling**: Create choose-your-own-adventure stories with multiple audio paths

### Design Customization

Ask an AI assistant to help you:
- Change fonts and colors
- Add album artwork for each track
- Create different layouts for different track types
- Add lyrics or transcripts below the audio player
- Include download buttons
- Add social sharing buttons

### Advanced Features

With AI help, you can add:
- Playlists that auto-advance to the next track
- Search functionality
- Categories/tags for tracks
- Password protection for certain tracks
- Analytics to see which tracks are most popular

## 🔧 Troubleshooting

### Audio doesn't play on iPhone

- Make sure the audio format is `.m4a` or `.mp3`
- iOS requires user interaction before audio plays (that's why there's a play button)
- Check that the file path in the `.md` file matches exactly (case-sensitive!)

### NFC tag doesn't work

- Verify the URL is correct (test by typing it manually in a browser)
- Make sure NFC is enabled on the phone
- Try rewriting the tag
- Some phone cases block NFC signals

### Background image doesn't show

- Check that the filename is exactly `background.png` (not `backround.png`)
- Verify the file is in `assets/` folder
- Try a different image format (`.jpg` also works)

### GitHub Pages isn't updating

- Changes can take 1-2 minutes to deploy
- Check the "Actions" tab in your repository for build status
- Make sure GitHub Pages is enabled in Settings

## 💡 Getting Help

If you run into issues:

1. **Check GitHub Pages build status**: Go to your repository's "Actions" tab
2. **Use AI assistants**: Paste error messages and ask for help
3. **Jekyll documentation**: https://jekyllrb.com/docs/
4. **GitHub Pages docs**: https://docs.github.com/en/pages

## 📝 Example AI Prompts for Customization

Here are some prompts you can use with AI assistants:

- *"I forked this audio player project. I have 15 audio files named [list]. Can you generate all the track .md files for me?"*
- *"How do I change the play button emoji to a different icon?"*
- *"Can you modify the CSS to make the cards dark themed with rounded corners?"*
- *"I want to add a subtitle field to each track. How do I modify track.html and the .md files?"*
- *"How can I organize tracks into categories like 'Stories' and 'Music'?"*

## 📜 License

Feel free to use this project for any purpose - personal, educational, or commercial.

## 🙏 Credits

Built with Jekyll and GitHub Pages. Designed for simplicity and ease of use with NFC technology.

---

**Ready to create your own audio experience? Fork this repo and start customizing! 🎵**