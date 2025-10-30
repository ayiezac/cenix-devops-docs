# How To Replicate the FILIPINO WOMEN Local Repo related to DevOps

1. Run `npm init` to initialize the package.json file. **If you already have this file, *skip this step.***
2. Install husky and lint-staged: `npm install --save-dev husky lint-staged`
3. Run `npx husky init`. In the .husky/pre-commit file, add: `npx lint-staged`
4. In `package.json`, under "scripts", add: `"lint:html": "npx html-validate www/**/*.html",` Also add this configuration: `"lint-staged": {	"www/**/*.html": [	"npm run lint:html"	]	}`

## Update Your GitHub YML File

1. Locate `{your-site}-local.yml` and `{your-site}-staging.yml` in `.github/workflows` and copy this GitHub workflow code:
    
    ```markdown
     env:
    	 HUSKY: 0
    	 
     jobs:
       build:
         runs-on: ubuntu-latest
         steps:
           - uses: actions/checkout@v5
    
           - name: Use Node.js
             uses: actions/setup-node@v4
             with:
               node-version: "22.x"
               cache: "npm"
           - run: npm ci
    
           - name: Linting HTML
             run: npm run lint:html
    ```
