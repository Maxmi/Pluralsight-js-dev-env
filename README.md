Notes I took following the "JavaScript development environment setup" on PluralSight.

1.  Create .editorconfig file in the root of the project.
2.  Create package.json file (http://bit.ly/jsdevpackagejson)
3.  Create npm scripts:

- "prestart" - will always run before npm start
- create script for security check and for sharing your work in progress(via localtunnel or alike)
- we can have scripts that will run in parallel(npm run all)
- and even will open an app in dev mode as well as for sharing at the same time

4.  Transpiling:
- Create .babelrc file and fill it. Now can change all 'require' statements to 'import'. But need to change npm scripts to start with 'babel-node' (instead of just 'node')

5. Bundling:
- Create webpack.config.dev.js file in the root of the project (http://bit.ly/2dSZwea). Note the output property of the object in the webpack file - bundle.js in src folder.  Now if we create a index.js file in src folder - webpack will see it as bundle.js, though will not physically create one.

6. Linting: 
 - can configure linting rules in the package.json
 - or create .eslintrc.json file in the root and add linting/watching script into package.json
 - you can set your own rules in the eslintrc file
 - if seeing warnings when running `npm run lint` - can add comments in `/* */` at the top of the file where that rule is not being followed - this will remove the warnings.
 - or can add a comment to the end of a single line - `// eslint-disable-line no-console`

7. Testing and CI:
 - tests can be located next to source file, not necessarily in separate 'test' folder
 - unit tests can be configured (in pkg.json) to run every time src files are saved
 - to setup Travis CI:
   - add the repo that needs to be watched to your account on Travis,
   - add .travis.yml file to the root
   - commit and push changes to Github. Travis will notify you on the status of changes(if your tests passed or failed);

8. HTTP Calls:
 - Libraries for making HTTP calls: 
    - in Node - http,request,  
    - in Browser - XMLHttpRequest, jQuery, Framework-based, Fetch
    - in Node&Browser - isomorphic-fetch, xhr, SuperAgent, Axios

It's often helpful to mock HTTP calls (unit tests, web services are not ready yet, services are slow, other testing purposes, etc).  
How to mock HTTP? - Nock, Static JSON, Create development webserver (api-mock, JSON server(static data), JSON schema faker(dynamic data), Browsersync, Express).
To use JSON schema: declare the schema, generate random data, serve data via API with JSON server
- Create mockDataSchema.js file with schema 
- Create generateMockData.js file 
- Add npm script to generate mock data
To get random data every time when we open the app - add "prestart-mockapi" npm script, then add "start-mockapi" to the "npm start" script.

9. Production Build
  - minification

10. Production Deploy

