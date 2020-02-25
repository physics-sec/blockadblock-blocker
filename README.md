# blockadblock-blocker
try to prevent the blockadblock from loading in any domain using Tampermonkey

### How to use
Paste the contents of the **blockadblock-blocker.js** file in a new userscript in [Tampermonkey](https://www.tampermonkey.net/index.php?) and you should be able to use adBlock freely.

### When not to use
If a site you like uses ads in a non-intrusive way, consider disabling this script while browsing it.

### If it doesn't work
If the creators of the blockadblocker change how their script works, then the *blockadblock-blocker.js* script might stop being able to detect it.
If that happens, open an Issue!

### How to adapt
You can edit in which sites this script excecutes with the `// @match        *://*/*` part of the script.  
`https://somesite.com/*` will only work on that site

