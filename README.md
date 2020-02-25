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

### How does it work?
The creators of the blockadblocker heavily obfuscated how their script works to make it harder to understand and bypass.  
When it loads, it does so in a script tag at the bottom of the page, usually you can see the following text at the beginning of the script:  
`// Place this code snippet near the footer of your page before the close of the /body tag`

The fist thing the script does, is call `eval` to deobfuscate the JavaScript code.  
The **blockadblock-blocker.js** creates a [Proxy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy) in the `eval` function and looks for certain key-words.  
If any of these keywords are found, then it decides that it is the blockadblocker trying to deobfuscate their script and returns undefined.  
If it does not find any of these keywords, then just calls the original eval and returns the result.


