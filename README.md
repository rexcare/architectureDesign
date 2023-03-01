# Todos v1

- [x] Replace model with controlnet and test it
- [x] Make UI look nicer, maybe dark theme
- [x] Redo landing page, remove testimonials and either make it dark mode or use another lp
- [x] Redo README
- [x] Fix issue with generations not working
- [x] Add two dropdowns for what kind of room it is + dropdown for themes
- [x] Use new redis db for rate limiting
- [x] Deploy, assign domain, fix meta tags, add OG image with one of the genrated pics
- [x] Tweet out a screenshot for hype
- [x] Let replicate team know to keep it on when I launch
- [x] Test it out locally + in prod to make sure it works properly
- [x] Add gradient for roomGPT
- [x] Refactor code in general (maybe use react-hook-form)
- [x] Some visual indication that it takes ~25s
- [x] Make sure original image doesn't stretch
- [x] add roomGPT domain
- [x] Email upload.io about changing the background for the upload component
- [x] Make sure the OG image is working
- [x] Move toggle slightly on the restore page and we took out the dropdowns
- [ ] Make sure it looks good on mobile (1, 2, 3 icons cut off)
- [ ] Test lighthouse scores to make sure I have good performance
- [ ] Maybe replace the pic in the homescreen and copy
- [ ] Add 1 more themes and types of rooms based on interiorAI
- [ ] Send it in Vercel's Slack to give folks a sneak peek

## Todos v2

- [ ] See if I should open a new tab when clicking "Upload new room"
- [ ] Add mechanism for folks to vote on themes with the top theme being added each week
- [ ] Add aggresive rate limiting
- [ ] Play around with the prompt based on levelsio project
- [ ] Test out other models and tweak params to obtain optimal results, might be tied to hough for faster generations
  - [ ] Try switching to 768px generations and seeing how that affects things
- [ ] Sharability features - look at Replicate's project for inspo
  - [ ] Add ability to generate shareable links – show
  - [ ] Also use dynamic OGs to make this work as well
- [ ] Add a carousel of generated rooms using my image gallery

Replicate ID should be stored in the URL ideally

<!-- // 1. User form with dropdowns for theme and room
// 2. Get back id from Replicate, tell it to switch to the second component, query with the id
// 3. Result component with the image and the download button -->

# [roomGPT.io](https://roomGPT.io)

This project generates new variations of your room based on a photo.

[![Room GPT](./public/screenshot.png)](https://roomGPT.io)

## How it works

It uses an ML model called [ControlNet](https://github.com/lllyasviel/ControlNet) to generate variations of rooms. This application gives you the ability to upload a photo of any room, which will send it through this ML Model using a Next.js API route, and return your generated room. The ML Model is hosted on [Replicate](https://replicate.com) and [Upload](https://upload.io) is used for image storage.

## Running Locally

### Cloning the repository the local machine.

```bash
git clone
```

### Creating a account on Replicate to get an API key.

1. Go to [Replicate](https://replicate.com/) to make an account.
2. Click on your profile picture in the top right corner, and click on "Dashboard".
3. Click on "Account" in the navbar. And, here you can find your API token, copy it.

### Storing API key in .env file.

Create a file in root directory of project with env. And store your API key in it, as shown in the .example.env file.

If you'd also like to do rate limiting, create an account on UpStash, create a Redis database, and populate the two environment variables in `.env` as well. If you don't want to do rate limiting, you don't need to make any changes.

### Installing the dependencies.

```bash
npm install
```

### Running the application.

Then, run the application in the command line and it will be available at `http://localhost:3000`.

```bash
npm run dev
```

## One-Click Deploy

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Nutlope/roomGPT&env=REPLICATE_API_KEY&project-name=room-GPT&repo-name=roomGPT)
