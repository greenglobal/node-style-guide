# Use ESLint and JSBeautify

## Table of contents

* [Install eslint ](#install-eslint)
* [Install js-beautify](#install-jsbeautify)
* [Install Atom's plugins ](#install-atoms-plugins)
* [Install Sublime Text's plugins](#install-sublime-texts-plugins)
* [ESLint configuration](#set-eslints-config)
* [JSBeautify configuration](#set-jsbeautifys-config)

#### GitHub repo:

https://github.com/GreenGlobalDevs/node-style-guide

#### Video:

[![Use ESLint and JSBeautify with Atom and Sublime Text ](http://i.imgur.com/Cpjqct6.png)](http://www.youtube.com/watch?v=hwmO5XAuDU0)



## Intro

ESLint and JSBeautify are the node.js packages that provide needed engine to check and format code. Primitively, they only have command line interface. But people can build GUI for them - in the format of plugins run on the source code editors like Atom and Sublime Text.

In order to install ESLint and JSBeautify, you must have node.js already. So the first step is go to [nodejs.org](https://nodejs.org) and install latest Node.js core. Rely on your platform, you can download .msi, .pkg or build from source.


## Install ESLint

Once you have got node.js, it's easy to install eslint with npm command:

Windows:

```
npm install -g eslint
```

![Install eslint in Windows 10](http://i.imgur.com/OpmaRRB.png)

Linux:

```
sudo npm install -g eslint
```

![Install eslint in Linux Mint 17.3](http://i.imgur.com/y4sxoN0.png)



## Install JSBeautify

Similar to eslint, we install js-beautify with npm command:

Windows:

```
npm install -g js-beautify
```

Linux:

```
sudo npm -g install js-beautify
```

![Install js-beautify in Linux Mint 17.3](http://i.imgur.com/33XvRlX.png)


Okay, if everything is OK, let's start installing needed plugins.


## Install Atom's plugins

We would need the following 3 plugins: [linter](https://github.com/atom-community/linter), [linter-eslint](https://github.com/AtomLinter/linter-eslint), and [atom-beautify](https://github.com/Glavin001/atom-beautify).

Edit --> Preferences --> Install:

![Start installing](http://i.imgur.com/NIfXIwd.png)

In the "Search packages" field, type "linter", then Enter, then scroll down to the package named "linter". Press "install" button at right side:

![Search and install linter](http://i.imgur.com/9JDqM8j.png)

Do same thing with linter-eslint and atom-beautify.

Search and install linter-eslint:

![Search and install linter-eslint](http://i.imgur.com/4p6UYaK.png)

Search and install atom-beautify:

![Search and install atom-beautify](http://i.imgur.com/frKAMBf.png)


## Install Sublime Text's plugins

With Sublime Text, we also need 3 plugins: [SublimeLinter](http://www.sublimelinter.com/en/latest/installation.html), [SublimeLinter-contrib-eslint](https://github.com/roadhump/SublimeLinter-eslint) and  [JsFormat](https://github.com/jdc0589/JsFormat).

Because Sublime Text does not have built-in package management tool, we need Package Control plugin first. Please follow [the intructions here](https://packagecontrol.io/installation) to install if not yet.

Then, from Sublime Text interface, press "Ctrl + Shift + P" to open Package Control menu, choose "Install Package".

![SublimeText - Install package](http://i.imgur.com/E7nxXcH.png)

In the empty field, type "SublimeLinter", then click on the matched item.

![SublimeText - Install SublimeLinter](http://i.imgur.com/OCgHzdx.png)

Do same thing with "SublimeLinter-contrib-eslint" and "JsFormat".

Search and install SublimeLinter-contrib-eslint:

![Search and install SublimeLinter-contrib-eslint](http://i.imgur.com/6BMhzyB.png)

Search and install JsFormat:

![Search and install JsFormat](http://i.imgur.com/BE54dW7.png)


## Set ESLint's config

The simplest way to configure ESLint to check your project's coding convention is make use the capability of "[ESLint Shareable Configs](http://eslint.org/docs/developer-guide/shareable-configs)" by following the guide here:

- [ESLint shareable config based on Green Global's JavaScript Style Guide](https://github.com/greenglobal/eslint-config-ggc)

After everything done, you can [download the examples](https://github.com/GreenGlobalDevs/node-style-guide/archive/master.zip) to see how it works. Extract downloaded .zip file, open it with Atom and browse to the JS files under /examples directory.

The following figures, I'm opening the project "node-style-guide" and "examples/bad.js", the result is really bad:

![Atom: bad.js](http://i.imgur.com/hFoz5LS.png)

Sublime Text gives the same result:

![Sublime Text: bad.js](http://i.imgur.com/YtU7lis.png)


#### Use CLI

You can clone this repo to run checking with command line:

```
git clone https://github.com/greenglobal/node-style-guide.git
cd node-style-guide
npm install
npm run lint
```

The result looks like this:

![Error while checking convention](http://i.imgur.com/o8QhR9W.png)

What we need to do here is fix the code until no any red flag appears :)

If the script file is too long, manual fixing may take a little time, you can use [JSBeautify](https://github.com/beautify-web/js-beautify) that supports auto formatting.


## Set JSBeautify's config

In the "node-style-guide" folder, you can see another file named ".jsbeautifyrc". This is config file used by atom-beautify plugin in Atom and JavaScript Beautify in Sublime Text. Each time when you press "Ctrl + Alt + B" or  "Ctrl + Alt + F"  key combination, these plugins can use JSBeautify core to reformat your source code. Unfortunately, this tool is not very powerful so it may leave some of the things that you need to fix by hand.


## Conclusion

In short, to follow convention, we would need to add 2 config files - .eslintrc.json and .jsbeautifyrc - into the root of project folder. Thus, the plugins of Atom and Sublime Text will handle about 80% of of the work for you.
