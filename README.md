# svelte-state-example-mynumbers

## About this project
- Have two components: App and Numbers
- Communicate between these components

## Quickstart
- git clone https://github.com/nvsx/svelte-state-example-mynumbers.git
- OR: degit nvsx/svelte-state-example-mynumbers svelte-state-example-mynumbers
- (degit: npm install -g degit)
- (degit: https://www.npmjs.com/package/degit) 
- cd svelte-state-example-mynumbers
- npm install
- npm run dev
- open http://localhost:5000

## About Svelte
- Homepage: https://svelte.dev/
- Svelte is a compiler, not a framework. 

## Howto work with SvelteJS
1. Have local NodeJS installation. Recommendation: Use NVM. 
	- For Linux and Mac: nvm, URL: https://github.com/nvm-sh/nvm
	- For Windows: nodist
2. Install degit to get starter files.
	- Command: "npm i -g degit"
	- Package: https://www.npmjs.com/package/degit
3. Start project with
	- "degit sveltejs/template myproject"
	- cd myproject
	- "atom ." or "code ."
4. Use IDE like Atom or Visual Studio Code
	- Install Package for syntax highlighting like "svelte-ide" or "Svelte"

## How to work with this project
There are two components:
- srv/App.svelte
- src/components/Mynumbers.svelte

Each component has three sections:
1. Script
2. HTML
3. Style

- There are comments in every component to explain what is going on. 

In the App component you see that Mynumbers component is embedded in HTML section.
- There are three attributes given to the Mynumbers component:
1. numbers (this is our number array)
2. on:click (this is ONE way to route an event between components)
3. add_num (a function that can be called from another component)

## How to get it running
1. npm install 
2. npm run dev
3. open http://localhost:5000
