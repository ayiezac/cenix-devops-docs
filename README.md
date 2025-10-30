# How To Replicate the FILIPINO WOMEN Local Repo
1. navigate to [filipino women github local repo](https://github.com/afafilo/filipino-women.com) and select local branch
2. install husky and lint-staged, `npm install --save-dev husky lint-staged`
3. run `npx husky init`, and in .husky/pre-commit file, put this npx lint-staged
4. in `package.json` , under "scripts", put this `"lint:html": "npx html-validate www/**/*.html",`, also add this 
	`"lint-staged": {
			"www/**/*.html": [
				"npm run lint:html"
			]
		}`
