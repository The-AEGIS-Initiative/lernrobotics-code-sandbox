# Requirements
Node.js:

[https://nodejs.org/en/download/](https://nodejs.org/en/download/)
# Usage
## Using npm
Obtain config.json file containing necessary API keys. Place `config.json` in the same directory as `app.js`.

\
Update node_modules with
#### `npm ci`
\
Start nodejs server using
#### `npm start`

## Using Docker
#### `docker run -p 8000:8000 -v /var/run/docker.sock:/var/run/docker.sock aegisinitiative/robobot-back-end:latest`



# Development Guidelines
Please read this section before making any changes!
<br />

## Contributing
#### Branch before making changes!
#### `git checkout -b <your-branch-name>`
\
Push the new branch to github and set it as the upstream branch using the `-u` option
#### `git push -u origin <your-branch-name>`
\
Make frequent commits (On your branch)

Each commit should be described easily in 1 line. Commits that require multiple lines should be split into smaller commits.
#### `git commit -m "<commit description>"`
\
Push commits to your upstream branch using
#### `git push`
\
Once your changes are complete and fully functional, create a merge request on github and ask someone to confirm it.
\
\
When your branch is no longer needed, you should delete it
#### `git branch -d <your-branch-name>`
Delete the upstream branch (<b>Do not delete branches that are not yours!</b>)
#### `git push origin --delete <your-branch-name>`
<br />

## Installing npm modules
Use --save when installing npm modules to ensure dependencies are installed locally.
#### `npm install --save <package-name>`
<br />

## Documenting Your Code
#### Document your code <b>BEFORE</b> pushing changes!

This project uses `jsdoc` (for javascript)

See [https://devhints.io/jsdoc](https://devhints.io/jsdoc) for jsdoc syntax
\
\
\
<b>BEFORE</b> pushing changes, generate html documentation files using
#### `npm run docs`
\
View current local documentation at
#### `docs/index.html`
\
View master branch documentation at
#### [https://teachrobo.github.io/back-end/](https://teachrobo.github.io/back-end/)


# Project File Structure

### Node.js server
##### `bin/www`
Entry point for browsers. Sets up http server to listens on specified port.
##### `routes/`
Contains all routes available on server. Each route serves as an API entry point.
##### `model/`
See MVC architecture. Contains database files.
##### `views/`
View templates in Jade. See MVC architecture.
##### `App.js`
Require and Use middlewares and Routes. Catch and handle errors.
##### `public/`
Assets available publicly. Includes Index.html which is served to the browser on load.
##### `package.json`
Config file for app-wide settings
##### `package-lock.json`
Contains all dependencies information
##### `node_modules`
Includes installed dependencies. Use npm ci to install correct dependency versions according to package-lock.json.
