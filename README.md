# Overview

This website is built using [SvelteKit](https://svelte.dev/docs/kit/introduction). Svelte code is
compliant with HTML, so you can copy and paste code from the main website into SvelteKit just fine
([with one exception](#html-compatibility-exception) that I know of). The website uses the
[static adapter](https://svelte.dev/docs/kit/adapter-static) so it can deployed using Github Pages.
The only difference this makes from traditional SvelteKit projects is that there's no server-side
code, but that shouldn't make a difference for this website.

# Table of Contents

- [HTML Compatibility](#html-compatibility-exception)
- [Running](#running)
- [Editing](#editing)
- [Project Structure](#project-structure)

## HTML Compatibility Exception

Svelte doesn't allow you to excute JavaScript in quotes. For example, in HTML, you can write code
like

```html
<script>
	function doSomething() {
		console.log('Something');
	}
</script>

<button onclick="doSomething()">Click Me</button>
```

However, in Svelte, you need to write it using curly braces.

```svelte
<script>
	function doSomething() {
		console.log('Something');
	}
</script>

<button onclick={doSomething}>Click Me</button>
```

If you need to pass arguments to the function, write it like this

```svelte
<script>
	function doSomething(message) {
		console.log(message);
	}
</script>

<button onclick={() => doSomething('Something')}>Click Me</button>
```

# Running

If you are just editing text, then [GitHub Codespaces](https://github.com/features/codespaces)
should work just fine. However, if you are making **ANY** UI changes, then you should preview the
website locally before publishing those changes.

## Tooling

You need [Node.js](https://nodejs.org/en) installed to view the website locally. If you do not have
Node.js installed, open the "terminal" app on you laptop and run these commands (copy and paste, the
press enter).

### Node.js

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
source "$HOME/.nvm/nvm.sh"
nvm install 24
```

To verify that the install suceeded, run these commands in the terminal.

```bash
node -v
npm -v
```

### Git

Now, you need to download the code. It's necessary to use [Git](https://git-scm.com/install/mac) to
update code when you make changes on your laptop. There are multiple methods, but the easiest (and
most space efficient) one is using [Homebrew](https://brew.sh/). To install using Homebrew, run
these commands in your terminal.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install git
```

Now, you can download the code using Git. If you don't have a directory specifically for code, I
would recommend just using the `Downloads` folder. Run these commands in your terminal.

```bash
cd ~/Downloads
git clone https://github.com/EHMD28/metrobots.github.io.git metrobots-sveltekit
cd metrobots-sveltekit
git checkout sveltekit
```

The line `git checkout sveltekit` is very important because I am **NOT** working on the main branch.
Alternatively, you could use the "Download ZIP" option on Github. Now, whenever you want to see the
current state of the website, open the project in Visual Studio Code and run this in the terminal.

```bash
npm run dev
```

If you want the most up-to-date changes, run this instead.

```bash
git pull --rebase
npm run dev
```

# Editing

Refer to [Project Structure](#project-structure) for details about where to place/edit files. The
recommended IDE for Svelte is [Visual Studio Code](https://code.visualstudio.com/) with the official
Svelte extension installed. I plan on making a proper style guide in the future.

# Project Structure

- `src/routes/` - All routes should be placed in this directory. In each route directory, except
  intermediate routes, there should be a `+page.svelte` file with the content for that page.

- `src/routes/+layout.svelte` - This page defines the layout for all subpages. This is where the
  navbar and footer code should be placed.

- `src/routes/+page.svelte` - This is the homepage of the website.

- `src/lib/assets/` - All images should be placed in an appropriate subdirectory. Prefer `.svg` files
  over `.png` or `.jpeg` when possible. They can be accessed in code using

- `src/lib/components` - All reusable Svelte components should be placed in this directory.

- `src/lib/index.js` - Any non-page-specific code should be placed in this file. I don't think it
  should be necessary for this project.

- `static/` - Location for files which need to be referenced statically rather than being imported.
