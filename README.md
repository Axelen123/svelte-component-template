# WebComponent template
---
# svelte component

This is a component template for [Svelte](https://svelte.dev). It lives at https://github.com/Axelen123/svelte-component-template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit Axelen123/svelte-component-template svelte-component
cd svelte-component
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*

## Get started

Install the dependencies...

```bash
cd svelte-component
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see a preview of your component running. Edit a component file in `src`, save it, and reload the page to see your changes.

## Usage

When you want to use the component you need too first build your app:

```bash
npm run build
```

**Svelte or with regular html**

Copy *public/bundle.js* and *public/bundle.js.map* to your server's asset folder:

```bash
cp public/bundle.js* YOUR_ASSETS_FOLDER
```

Include the script and component in your html file:

```html
<script src="bundle.js"></script>
<svelte-component name="WebComponents"></svelte-component>
<!--
You can change the name of the tag by editing rollup.config.js and index.html.
-->
```

**Angular**

Make a directory in *src* called *web-components*

Edit your module file:
```ts
import { NgModule, CUSTOM_ELEMENTS_SCHEMA } from '@angular/core';
 
import '../web-components/YOUR_COMPONENT_JS';
 
@NgModule({
  declarations: [
    // Your Angular components
  ],
  imports: [
    // Your imports
  ],
  providers: [
      // Your providers
  ],
  schemas: [
    CUSTOM_ELEMENTS_SCHEMA
  ]
})
export class YourModule { }
```

Edit your *tsconfig.json*:
```json
{
    "compilerOptions": {
        "allowJs": true
    }
}
```