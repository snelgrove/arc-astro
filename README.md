# Minimal Astro Project 
This is a minimal Astro project, which demonstrates a strange issue when deployed to AWS. When hosted within an Architect project, the route `/_snowpack/pkg/@astrojs.renderer-svelte.client.v0.1.1.js` intermittently results in a `400 Bad Request` response.

## Setup
- Run the `build` script in the `/site` directory, to build the Astro site to `/site/public`
- Manually copy `/site/public` to `/public`, which is managed by the Arc project
- Deploy the Arc project
- Disable SPA in Arc < 9 using ARC_STATIC_SPA = false


# Possible Prerequisites
- Does the initial deployment _have_ to be performed on Arc 8.7.4?
- Does the offending file _have_ to begin with the '@' character?
- Does the URL path have to be at least on directory down from the root?
- Any given browser tab seems to receive a response from the same IP for an extended period of time - If it doesn't fail initially, that tab probably won't fail. Curl does not exhibit this bevahiour
