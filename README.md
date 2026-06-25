# How to Build My 3D Portfolio Website (Step-by-Step, Simple Guide)

This is a plain-language walkthrough. No fancy words — just the actual steps, in order, from "nothing" to "a live website with a video on it."

There are two parts:
1. **Make the video** (the one that plays in the hero section)
2. **Make the website** (using that video, with cool 3D scenes)

---

## Part 1: Making the Hero Video

The hero video is the first thing people see — you sitting at your desk, talking, with code on screen behind you.

### Step 1 — Decide what the video should show
Keep it simple. The video should show:
- You at your desk, computer screens with code/diagrams visible
- Warm, cozy lighting (like a late-night coding session)
- You gesturing like you're explaining something
- No long talking — it loops in the background, so 5-10 seconds is enough

### Step 2 — Generate the video using Higgsfield
1. Open Higgsfield (the video/image tool)
2. Use your reference photo (the one of you at the desk) as the starting image
3. Ask it to generate a short video from that image — keep the person mostly still, maybe slight hand movement, camera staying steady
4. Pick a video model good for "image to video" with realistic, subtle motion (not big dramatic camera moves — the website is already adding 3D motion on top)
5. Generate a few versions and pick the best one

### Step 3 — Clean it up
1. If the video has any sound you don't want, mute it (the website will autoplay it muted anyway)
2. If it's too long, trim it down to 5-10 seconds and loop it
3. Compress the file so it's small (under 8MB) — a smaller file means the website loads fast. You can use Higgsfield's own export, or a free online video compressor

### Step 4 — Save the final file
Name it something simple like `hero-video.mp4` and keep it somewhere easy to find — you'll need to upload it when we build the site.

---

## Part 2: Building the Website

### Step 1 — Get the building blocks ready
You already have:
- The big "master prompt" document that describes the whole site (sections, colors, fonts, your job history)
- A separate prompt just for "Scene 3" (the floating skills graph)
- The hero video from Part 1

Think of these as the *instructions*. Claude Code is the *builder* that reads the instructions and writes the actual website code.

### Step 2 — Open Claude Code
This is the tool that turns your written instructions into a real, working website. Open it in your project folder (a new empty folder is fine — Claude Code will create everything inside it).

### Step 3 — Hand over the main prompt
Paste in the full master prompt (the one with all four scenes, your job history, the colors, etc.) and tell Claude Code to build the site. Since Claude Code already has the `ui-ux-pro-max` skill installed, it'll use that automatically for the layout and design polish — no extra step needed there.

### Step 4 — Let it build
Claude Code will:
- Set up the Next.js project (the framework the site runs on)
- Install the 3D tools (React Three Fiber, GSAP, Framer Motion)
- Build each section: Hero, About, Experience, Skills, Education, Contact
- Wire up the scroll animations so the camera "flies through" the 3D world as you scroll

This takes a while — let it work. If it asks you questions along the way (like where to put a file, or which color to use), answer them.

### Step 5 — Add your hero video
When Claude Code asks for the hero video (or when you reach the hero section), give it the `hero-video.mp4` file from Part 1. It'll place it in the right spot and wire it up as the background.

### Step 6 — Build Scene 3 separately (the skills graph)
Paste in the separate Scene 3 prompt and ask Claude Code to build that specific piece — the floating skill nodes that light up when you hover over a skill card. This can be done right after the main build, as its own focused step.

### Step 7 — Preview it
Once it's built, run the site locally (Claude Code will tell you the command, usually something like "run the dev server") and open it in your browser. Scroll through the whole thing and check:
- Does the video play smoothly in the hero?
- Do the 3D scenes look right as you scroll?
- Does hovering a skill card light up the matching node in Scene 3?
- Is your job history accurate and in the right order?

### Step 8 — Fix anything that looks off
If something's wrong (a typo, a color you don't like, an animation that's too fast), just tell Claude Code in plain language what to change. It'll edit the code directly — you don't need to touch any code yourself.

### Step 9 — Push the code to GitHub
Once you're happy with it, ask Claude Code to push the project to your GitHub account (`Ajkolaganti`) so it's saved and backed up.

### Step 10 — Deploy it live
Connect the GitHub repo to Vercel (or ask Claude Code to do it for you). Vercel will give you a live web link you can share — something like `yourname.vercel.app`, or your own domain if you point one at it.

---

## Quick Recap (the whole thing in 5 lines)

1. Generate a short video of yourself at your desk using Higgsfield
2. Hand your master prompt + that video to Claude Code
3. Let Claude Code build the full site, then build Scene 3 separately
4. Preview it, ask for fixes in plain language until it looks right
5. Push to GitHub, deploy on Vercel, share the link

---

## If Something Goes Wrong

- **Video doesn't play on the live site** → it's probably too big a file size. Compress it smaller and re-upload.
- **3D scenes look laggy/slow** → tell Claude Code to reduce the number of floating shapes/particles — fewer objects = smoother on most computers.
- **Site looks broken on phone** → tell Claude Code "this needs to work well on mobile too" and point out exactly what looks wrong.
- **You don't like a color or font** → just say so in plain words ("make the orange more red" or "make the headline bigger") — no need to know any technical terms.
