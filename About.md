# Proof of Concept

This is fork is a proof of concept for migrating from pure HTML/CSS/JS to
[SvelteKit](https://svelte.dev/docs/kit/introduction). This fork SHOULD NOT be merged with the
original repository. I think switching to Svelte will make implementing changes in the future much
easier.

If you want to see a more complete SvelteKit project, see [my personal website](https://ehmd28.github.io).

## Advantages

### Just HTML/CSS/JS

All valid HTML/CSS/JS is valid Svelte code, so it's more-or-less a drop-in replacement. All pages
just need to be placed into the `routes/` directory, and all `index.html` files need to be renamed
to `+page.svelte`. There are some useful Svelte specific features, but these can be integrated
incremetally rather than all at once.

### Shared layout across pages

SvelteKit offers `+layout.svelte`, for defining a shared layout for all pages. This can be used to
have a shared navbar or footer across pages without repeating code.

```svelte
<!-- src/routes/+layout.svelte -->
<nav>
    <h2>About Us</h2>
    <h2>Our Season</h2>
    <h2>Our Community</h2>
    <h2>Resources</h2>
</nav>

<!-- Render the content of the current page -->
{@render children()}

<footer>
    <img src="instagram-link" alt="instagram" />
    <img src="github-link" alt="github" />
    <img src="twitter-link" alt="twitter" />
    <img src="youtube-link" alt="youtube" />
    <img src="email-link" alt="email" />
</footer>
```

### Reusable Components

SvelteKit can be used to create reusable visual components with their own CSS and Javascript.

```svelte
<!-- src/lib/components/Navbar.svelte -->
<script>
    function someFunction() {
        console.log("Some code related to the navbar.");
    }
</script>

<nav>
    <h2>About Us</h2>
    <h2>Our Season</h2>
    <h2>Our Community</h2>
    <h2>Resources</h2>
    <button onclick={someFunction}>Some Button In the Navbar</button>
</nav>

<style>
    nav {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-around;
    }
</style>
```

This component can then be used in a page like this.

```svelte
<script>
    import Navbar from "$libs/components/Navbar.svelte";
</script>

<Navbar />

<!-- Render the content of the current page -->
{@render children()}

<footer>
    <img src="instagram-link" alt="instagram" />
    <img src="github-link" alt="github" />
    <img src="twitter-link" alt="twitter" />
    <img src="youtube-link" alt="youtube" />
    <img src="email-link" alt="email" />
</footer>
```

## Disadvantages

### Higher Barrier to Entry

There is a slight learning curve to using Svelte over HTML/CSS/JS (understanding project structure,
resusable componets, etc.). I do think SvelteKit has good documentation, but it's still important to
take this into account.

### Requires More Tooling

While a website made using HTML can be opened using any browser, it's necessary to have [Node.js](https://nodejs.org/en/download)
installed when using SvelteKit. This is mainly for UI changes rather than just text changes. There is
an official Visual Studio Code [extension](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)
for Svelte.

```bash
# To view the website locally, run this command.
npm run dev
```
