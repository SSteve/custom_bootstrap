# Customizing Bootstrap

## Instructions from YouTube video

[This video](https://youtu.be/siHIdLVtBtI)

- Create a new project folder.
- Open project folder in VS code.
- Create index.html.
- Use '!' + tab to create skeleton html file.
- Open index.html with Live Server.
- Go into the project folder and initialize an npm project.
        npm init -y
- Install Bootstrap.
        npm install bootstrap --save
	- Note: video had `npm install bootstrap@next --save` but I got the error "No matching version found for bootstrap@next." Perhaps that's because this was made when 4 was still the current Bootstrap version and you needed to add "@next" to get early releases of 5. In the video it installed 5.0.0-alpha1. Today (2022-05-24), it installed 5.1.3.
- This creates the *node_modules* folder which contains *bootstrap*.
- Install Sass compiler. (In the video, he installs node-sass, but the Bootstrap project has switched to Dart Sass, so I'm installing that one.)
        npm install sass --save
- In *package.json*:
	- Add a comma to the end of the "test" line under "scripts".
	- Below that line, add `"scss": sass --watch scss:css`.
		- This is different syntax than node-sass.
- Create the *custom_bootstrap.scss* file in the *scss* folder as described above.
- Create a *css* folder.
- On the command line, issue the command `npm run scss`.
- There should now be a *custom_bootstrap.css* file that has the customized Bootstrap css.

## Minify the custom Bootstrap css.

- Install minifier app
        npm install css-minify
		
- Add `minify` task to *package.json* scripts. (Add a comma after the end of the last script.)
        "minify": "css-minify -f css/custom_bootstrap.css"
		
- Run the minify task in the terminal.
        npm run minify
