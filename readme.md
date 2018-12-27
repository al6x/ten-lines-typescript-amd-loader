If you use TypeScript in Browser - there's no need to use Babel, WebPack, require.js, almond.js, System.js.

All you need to do is to add following lines to `tsconfig.json` file:

``` json
{
  "compilerOptions": {
    "module": "AMD",
    "outFile": "./build/app.js",
  }
}
```

and require the `app.js` in `index.html` like that:

``` html
  <script type="text/javascript" src="/ten-lines-typescript-amd-loader.js"></script>
  <script type="text/javascript" src="/build/app.js"></script>
```

That's all. Very easy setup for small projects when you don't need to bother with optimised WebPack build, and don't 
want to spend time setting up old and overengineered shit like Babel, require.js, almond.js, System.js

A little more details
=====================

You cant tell TypeScript to watch over your project and recompile the build on the fly `tsc -w` and in start
static web server in another terminal tab `http-server -c-1 .` - all done, now just open your `index.html` with
assembled app in Browser.
