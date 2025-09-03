# .gitignore

```
node_modules

# Output
.output
.vercel
.netlify
.wrangler
/.svelte-kit
/build

# OS
.DS_Store
Thumbs.db

# Env
.env
.env.*
!.env.example
!.env.test

# Vite
vite.config.js.timestamp-*
vite.config.ts.timestamp-*

```

# .npmrc

```
engine-strict=true

```

# .prettierignore

```
# Package Managers
package-lock.json
pnpm-lock.yaml
yarn.lock
bun.lock
bun.lockb

# Miscellaneous
/static/

```

# .prettierrc

```
{
	"useTabs": true,
	"singleQuote": true,
	"trailingComma": "none",
	"printWidth": 100,
	"plugins": [
		"prettier-plugin-svelte"
	],
	"overrides": [
		{
			"files": "*.svelte",
			"options": {
				"parser": "svelte"
			}
		}
	]
}

```

# package.json

```json
{
	"name": "minor-bibdem",
	"private": true,
	"version": "0.0.1",
	"type": "module",
	"scripts": {
		"dev": "vite dev",
		"build": "vite build",
		"preview": "vite preview",
		"prepare": "svelte-kit sync || echo ''",
		"check": "svelte-kit sync && svelte-check --tsconfig ./tsconfig.json",
		"check:watch": "svelte-kit sync && svelte-check --tsconfig ./tsconfig.json --watch",
		"format": "prettier --write .",
		"lint": "prettier --check .",
		"test:unit": "vitest",
		"test": "npm run test:unit -- --run"
	},
	"devDependencies": {
		"@sveltejs/adapter-static": "^3.0.8",
		"@sveltejs/kit": "^2.22.0",
		"@sveltejs/vite-plugin-svelte": "^6.0.0",
		"@vitest/browser": "^3.2.3",
		"playwright": "^1.53.0",
		"prettier": "^3.4.2",
		"prettier-plugin-svelte": "^3.3.3",
		"svelte": "^5.0.0",
		"svelte-check": "^4.0.0",
		"typescript": "^5.0.0",
		"vite": "^7.0.4",
		"vitest": "^3.2.3",
		"vitest-browser-svelte": "^0.1.0"
	},
	"dependencies": {
		"rfs": "^10.0.0",
		"sass": "^1.91.0"
	}
}

```

# README.md

```md
# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

\`\`\`sh
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
\`\`\`

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

\`\`\`sh
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
\`\`\`

## Building

To create a production version of your app:

\`\`\`sh
npm run build
\`\`\`

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

```

# src\_header.scss

```scss
header {
    nav {
        display: flex;
        justify-content: space-between;
        width: 100%;
        position: fixed;
        top: 0;
        overflow: hidden;
        padding: 4rem;

        color: white;

        .nav-btns {
            display: flex;
            justify-content: space-between;
            gap: 2rem;

            :last-child {
                // @include padding($reg-space);
                padding: $reg-space;
                border: white 1px solid;
                border-radius: 9px;
            }
        }
    }
}

.hero {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: center;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    background-size: cover !important;
    background:
        linear-gradient(
            to bottom, 
            rgba(0, 0, 0, 0.35) 0%,  
            rgba(0, 0, 0, 0.1) 100%),
        url(/src/lib/assets/BibDem_Titelbild_no-text.png) no-repeat center center scroll;

        h1, h2 {
            color: white;
        }
}

```

# src\_reset.scss

```scss
@import url('https://fonts.googleapis.com/css2?family=Libre+Franklin:ital,wght@0,100..900;1,100..900&display=swap');

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

// :root {
//   --sans-serif: 'Libre Franklin', sans-serif;

//   --color-bg: hsl(220, 20%, 14%);
//   --color-text: hsl(0, 0%, 2%);
//   --color-title: hsl(357, 49%, 48%);
//   --color-highlight: hsl(0, 33%, 64%);
//   --color-gray-28: hsl(0, 0%, 28%);
//   --color-gray-58: hsl(0, 0%, 58%);
//   --color-gray-90: hsl(0, 0%, 90%);

//   --font-24: 1.5rem;
//   --font-32: 2rem;
//   --font-80: 5rem;

//   --spacing-4: 0.25rem;
//   --spacing-8: 0.5rem;
//   --spacing-16: 1rem;

//   --shadow-1: hsl(0, 0%, 0%, 0.1);

//   --radius-base: 4px;
// }

html,
body {
  height: 100%;
  font-family: 'Libre Franklin';
}

label,
input,
button {
  font-family: inherit;
  font-weight: inherit;
  line-height: inherit;
  color: inherit;
}

button {
  background: none;
  border: 0;
  cursor: pointer;
}

.hidden {
  visibility: hidden;
}

```

# src\_typography.scss

```scss

```

# src\_variables.scss

```scss
@import "../node_modules/rfs/scss";



$primary: #444C9A;
$secondary: #E84C37;

.primary {
    color: $primary;
}

.secondary {
    color: $secondary;
}



/*-----Typography-----*/

$font-size-sm: 1rem;
$font-size-basis: 1.2rem;
$font-size-lg: 1.5rem;
$font-size-xl: 3.8rem;

$line-height: 1.5;
$chperline: 70ch;
$smaller-text: 80%;
$bigger-text: 120%;



%font-sm {
  @include font-size($font-size-sm);
}

%font-reg {
  @include font-size($font-size-basis);
}

%font-lg {
  @include font-size($font-size-lg);
}

p {
  @extend %font-reg;
}

h1 {
  @include font-size($font-size-xl)
}

h2 {
  @include font-size($font-size-lg);
  font-weight: 300;
}

h3 {
  @include font-size($font-size-basis);
}

/*-----Paddings & Gap-----*/

$reg-space: 2rem;
$sm-space: calc($reg-space / 2);
$xs-space: calc($sm-space / 2);
$xxs-space: calc($xs-space / 2);
$lg-space: calc($reg-space * 2);
$padding-btn: $sm-space $xs-space;
```

# src\app.d.ts

```ts
// See https://svelte.dev/docs/kit/types#app.d.ts
// for information about these interfaces
declare global {
	namespace App {
		// interface Error {}
		// interface Locals {}
		// interface PageData {}
		// interface PageState {}
		// interface Platform {}
	}
}

export {};

```

# src\app.html

```html
<!doctype html>
<html lang="en">
	<head>
		<meta charset="utf-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
		%sveltekit.head%
	</head>
	<body data-sveltekit-preload-data="hover">
		<div style="display: contents">%sveltekit.body%</div>
	</body>
</html>

```

# src\demo.spec.ts

```ts
import { describe, it, expect } from 'vitest';

describe('sum test', () => {
	it('adds 1 + 2 to equal 3', () => {
		expect(1 + 2).toBe(3);
	});
});

```

# src\index.css

```css
@import url("https://fonts.googleapis.com/css2?family=Libre+Franklin:ital,wght@0,100..900;1,100..900&display=swap");
.primary {
  color: #444C9A;
}

.secondary {
  color: #E84C37;
}

/*-----Typography-----*/
p {
  font-size: 1.2rem;
}

h1 {
  font-size: calc(1.505rem + 3.06vw);
}
@media (min-width: 1200px) {
  h1 {
    font-size: 3.8rem;
  }
}

h2 {
  font-size: calc(1.275rem + 0.3vw);
  font-weight: 300;
}
@media (min-width: 1200px) {
  h2 {
    font-size: 1.5rem;
  }
}

h3 {
  font-size: 1.2rem;
}

/*-----Paddings & Gap-----*/
header nav {
  display: flex;
  justify-content: space-between;
  width: 100%;
  position: fixed;
  top: 0;
  overflow: hidden;
  padding: 4rem;
  color: white;
}
header nav .nav-btns {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
}
header nav .nav-btns :last-child {
  border: white 1px solid;
  border-radius: 9px;
}

.hero {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: center;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  background-size: cover !important;
  background: linear-gradient(to bottom, rgba(0, 0, 0, 0.35) 0%, rgba(0, 0, 0, 0.1) 100%), url(/src/lib/assets/BibDem_Titelbild_no-text.png) no-repeat center center scroll;
}
.hero h1, .hero h2 {
  color: white;
}

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  font-family: "Libre Franklin";
}

label,
input,
button {
  font-family: inherit;
  font-weight: inherit;
  line-height: inherit;
  color: inherit;
}

button {
  background: none;
  border: 0;
  cursor: pointer;
}

.hidden {
  visibility: hidden;
}/*# sourceMappingURL=index.css.map */
```

# src\index.css.map

```map
{"version":3,"sources":["_reset.scss","_variables.scss","index.css","../node_modules/rfs/scss.scss","_header.scss"],"names":[],"mappings":"AAAQ,mHAAA;ACOR;EACI,cAJM;ACDV;;ADQA;EACI,cAPQ;ACEZ;;ADUA,uBAAA;AAkBA;EE4PM,iBALI;AD9QV;;ADmCA;EEoPQ,kCAAA;ADnRR;ACuHI;EFxFJ;IE2PQ,iBAAA;EDtRN;AACF;;AD8BA;EEgPQ,iCAAA;EF9ON,gBAAA;AC3BF;AC6GI;EFpFJ;IEuPQ,iBAAA;ED5QN;AACF;;ADyBA;EEuOM,iBALI;ADvPV;;ADyBA,2BAAA;AG3DI;EACI,aAAA;EACA,8BAAA;EACA,WAAA;EACA,eAAA;EACA,MAAA;EACA,gBAAA;EACA,aAAA;EAEA,YAAA;AFqCR;AEnCQ;EACI,aAAA;EACA,8BAAA;EACA,SAAA;AFqCZ;AEnCY;EACI,uBAAA;EACA,kBAAA;AFqChB;;AE/BA;EACI,aAAA;EACA,uBAAA;EACA,mBAAA;EACA,sBAAA;EACA,kBAAA;EACA,WAAA;EACA,aAAA;EACA,gBAAA;EACA,iCAAA;EACA,yKACI;AFiCR;AE3BQ;EACI,YAAA;AF6BZ;;AFtEA;;;EAGE,SAAA;EACA,UAAA;EACA,sBAAA;AEyEF;;AF9CA;;EAEE,YAAA;EACA,6BAAA;AEiDF;;AF9CA;;;EAGE,oBAAA;EACA,oBAAA;EACA,oBAAA;EACA,cAAA;AEiDF;;AF9CA;EACE,gBAAA;EACA,SAAA;EACA,eAAA;AEiDF;;AF9CA;EACE,kBAAA;AEiDF","file":"index.css"}
```

# src\index.scss

```scss
@use "variables";
@use "typography";
@use "reset";

@use "header";



```

# src\lib\assets\BibDem_Titelbild_no-text.png

This is a binary file of the type: Image

# src\lib\assets\favicon.svg

This is a file of the type: SVG Image

# src\lib\index.ts

```ts
// place files you want to import through the `$lib` alias in this folder.

```

# src\routes\+layout.svelte

```svelte
<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import "../index.css";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children?.()}

```

# src\routes\+page.svelte

```svelte
<header>
  <nav>
      <p>
        Minor: Projektkontor
      </p>
      <div class="nav-btns">
          <button>Ausstellung</button>
          <button>Projektkontext</button>
          <button>Förderung</button>
          <button>Kontakt</button>
      </div>
  </nav>
</header>

<section class="hero">
    <h1>Bibliotheken als Orte der Demokratiegeschichte</h1>
    <h2>Eine partizipative Recherche von Nutzer*innen der Amerika-Gedenkbibliothek in Berlin</h2>
</section>

```

# src\routes\page.svelte.spec.ts

```ts
import { page } from '@vitest/browser/context';
import { describe, expect, it } from 'vitest';
import { render } from 'vitest-browser-svelte';
import Page from './+page.svelte';

describe('/+page.svelte', () => {
	it('should render h1', async () => {
		render(Page);
		
		const heading = page.getByRole('heading', { level: 1 });
		await expect.element(heading).toBeInTheDocument();
	});
});

```

# static\robots.txt

```txt
# allow crawling everything by default
User-agent: *
Disallow:

```

# svelte.config.js

```js
import adapter from '@sveltejs/adapter-static';
import { vitePreprocess } from '@sveltejs/vite-plugin-svelte';

/** @type {import('@sveltejs/kit').Config} */
const config = {
	// Consult https://svelte.dev/docs/kit/integrations
	// for more information about preprocessors
	preprocess: vitePreprocess(),
	kit: { adapter: adapter() }
};

export default config;

```

# tsconfig.json

```json
{
	"extends": "./.svelte-kit/tsconfig.json",
	"compilerOptions": {
		"allowJs": true,
		"checkJs": true,
		"esModuleInterop": true,
		"forceConsistentCasingInFileNames": true,
		"resolveJsonModule": true,
		"skipLibCheck": true,
		"sourceMap": true,
		"strict": true,
		"moduleResolution": "bundler"
	}
	// Path aliases are handled by https://svelte.dev/docs/kit/configuration#alias
	// except $lib which is handled by https://svelte.dev/docs/kit/configuration#files
	//
	// To make changes to top-level options such as include and exclude, we recommend extending
	// the generated config; see https://svelte.dev/docs/kit/configuration#typescript
}

```

# vite.config.ts

```ts
import { sveltekit } from '@sveltejs/kit/vite';
import { defineConfig } from 'vite';

export default defineConfig({
	plugins: [sveltekit()],
	test: {
		expect: { requireAssertions: true },
		projects: [
			{
				extends: './vite.config.ts',
				test: {
					name: 'client',
					environment: 'browser',
					browser: {
						enabled: true,
						provider: 'playwright',
						instances: [{ browser: 'chromium' }]
					},
					include: ['src/**/*.svelte.{test,spec}.{js,ts}'],
					exclude: ['src/lib/server/**'],
					setupFiles: ['./vitest-setup-client.ts']
				}
			},
			{
				extends: './vite.config.ts',
				test: {
					name: 'server',
					environment: 'node',
					include: ['src/**/*.{test,spec}.{js,ts}'],
					exclude: ['src/**/*.svelte.{test,spec}.{js,ts}']
				}
			}
		]
	}
});

```

# vitest-setup-client.ts

```ts
/// <reference types="@vitest/browser/matchers" />
/// <reference types="@vitest/browser/providers/playwright" />

```

