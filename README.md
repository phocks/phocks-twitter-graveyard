# phocks-twitter-graveyard

Just a proof-of-concept for now, since I've stopped posting on the bird site, I wanted to make a kind of memorial type page out of the exported twitter data.

For now it's simply a random tweet of around 75,000 between the years 2007 and 2023.

Refresh the page for a new random tweet.

(I'll put it on a proper domain later ok)

[https://phocks-twitter-graveyard.pages.dev/](https://phocks-twitter-graveyard.pages.dev/)

## Development

Build with `npm run build`. This will build to the `dist` directory.

Deployment is to Cloudflare Pages and uses wranger to deploy.

Basically do `npx wrangler login` and follow the login instructions.

Then try `npx wrangler pages deploy dist/` to deploy the site.