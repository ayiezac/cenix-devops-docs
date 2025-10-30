# How To Replicate the FILIPINO WOMEN Local Repo related to DevOps

1. please run `npm init` to initialize the package.json file, **if you have you already this file, *kindly skip this step*** 
2. install husky and lint-staged, `npm install --save-dev husky lint-staged`
3. run `npx husky init`, and in .husky/pre-commit file, put this `npx lint-staged`
4. in `package.json` , under "scripts", put this `"lint:html": "npx html-validate www/**/*.html",`, also add this 
	`"lint-staged": {
			"www/**/*.html": [
				"npm run lint:html"
			]
		}`
