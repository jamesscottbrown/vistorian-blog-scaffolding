# Vistorian Blog project scaffolding code

# Running the server code

I have made modifications in a separate branch of the Vistorian monorepo.

To run the modified code, install `npm`, then install `lerna`:

```bash
npm install -g lerna
```

Then:

```bash

git clone git@github.com:networkcube/vistorian-monorepo.git
cd vistorian-monorepo
git checkout blog-integration
lerna bootstrap

cd packages/vistorian-web-sveltekit
npm run dev
```

### Running this code

Clone this repository.

You will need to start a local web-server to serve it's contents - see the [big list of http static server one liners](https://gist.github.com/willurd/5720255).

I suggest using `python3 -m http.server 8000`, or doing `npm install -g http-server` then running `http-server`.

If the server is running on a port other than `8081` you will need to modify [the relevant URL in `packages/vistorian-web-sveltekit/src/components/bookmarks/Logbook.svelte`](https://github.com/networkcube/vistorian-monorepo/blob/382184d5e66b83687967be3e8823a191d132319a/packages/vistorian-web-sveltekit/src/components/bookmarks/Logbook.svelte#L180).

### Transferring data

Open the Vistorian by navigating to http://localhost:3000 in your preferred web-browser.
Visiting the homepage will load the `demo_scientists` dataset into the browser's LocalStorage. You can then click "Start my Session", select this dataset, and select a visualisation.

Click the "Expand" button on the floating Bokmarks panel, and add a new bokmark.

You can then click the new `Push bookmarks to blog editor` button (which is only available in the `blog-integration` branch).

If everything is set up correctly, this will open the page served from this repo, which will display the network data and saved bookmarks.

In the actual blog application, the blob of JSON describing the bookmarks would be used to populated a list from which the user can select a bookmark to insert into a blog entry.


