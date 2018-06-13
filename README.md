Notes I took following the Pluralsig course on JavaScript development environment setup.

1.  Create .editorconfig file in the root of the project.
2.  Create package.json file (http://bit.ly/jsdevpackagejson)
3.  Create npm scripts:

- "prestart" - will always run before npm start
- create script for security check and for sharing your work in progress(via localtunnel or alike)
- we can have scripts that will run in parallel(npm run all)
- and even will open an app in dev mode as well as for sharing at the same time

4.  Create .babelrc file and fill it. Now can change all 'require' statements to 'import'. But need to change npm scripts to start with 'babel-node' (instead of just 'node')
5. Create webpack.config.dev.js file in the root of the project (http://bit.ly/2dSZwea). Note the output property of the object in the webpack file - bundle.js in src folder.  Now if we create a index.js file in src folder - webpack will see it as bundle.js, though will not physically create one.
6. 
