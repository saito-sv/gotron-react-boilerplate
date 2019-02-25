# gotron-react-boilerplate

A minimalistic boilerplate for [gotron](https://github.com/Equanox/gotron) and [reactjs](https://github.com/facebook/react). Tested on Windows, macOS and Linux.

This project contains only bare minimum of tooling and dependencies to provide you with simple to understand and extensible base (but still, this is fully functional).

# Quick start

Make sure you have [Node.js](https://nodejs.org) installed, then type the following commands known to every Node developer...

```
git clone https://github.com/Marlon-Monroy/gotron-react-boilerplate.git
cd gotron-react-boilerplate/ui
npm install
npm start
```

if you are using yarn

```
git clone https://github.com/Marlon-Monroy/gotron-react-boilerplate.git
cd gotron-react-boilerplate/ui
yarn
yarn start
```

This will download all the dependencies needed for react to work.

# Structure of the project

The application consists of...

`ui` - Where all the ui and react related files live).

The build process compiles the content of the `src` folder and puts it into the `dist` folder, so after the build has finished, your `dist` folder contains the full, runnable application.

I've used `mod` for go depencency manager but i figured you might want to use something different so ive added the
`go.mod` and `go.sum` files to `.gitignore` feel free to make changes as needed.

# Development

## Starting the app

```
go run main.go
```

## The build pipeline

Build process uses [Webpack](https://webpack.js.org/). The entry-points is `src/index.js`. Webpack will follow all `import` statements starting from those files and compile code of the whole dependency tree into one `.js` file for each entry point.

[Babel](http://babeljs.io/) is also utilised.

_Side note:_ Im using `react 16.7.alpha2` so that i can use hook.

## Updating react version

To do so edit `ui/package.json`:

```json
"dependencies": {
  "react": "16.7"
}
```

## Adding npm modules to your app

Remember to respect the split between `dependencies` and `devDependencies` in `package.json` file. Your distributable app will contain modules listed in `dependencies` after running the release script.

# Making a release

To package your app:

```
cd gotron-react-boilerplate/ui
npm run build
```

Once the packaging process finished, the `dist` directory will contain your distributable file.
