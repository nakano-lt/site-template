# Site template

A lean, gulp-based HTML & SASS boilerplate for better front-end coding of nakano_lt.

Based on: <http://sanographix.github.io/rin/> (Thanks!!!!)

# Getting Started

### Required Components

- Node.js
    - <http://nodejs.org/>
    - v0.12.x is recommended.

## Set Up

#### 1) Install gulp:

*Note:* If you have already installed gulp, skip this section.

    $ npm install -g gulp

#### 2) Fork this and rename that:

#### 3) Clone the repo:

    $ git clone...
    $ cd ...
    $ npm install

#### 4) Run gulp:

    $ gulp

#### 4) Edit event.json, site.json, talks.json

#### 5) :tada:

<hr/>

# Directory

While you are running Rin, It is watching directories under `templates/`, `sass/`, `js/`, `images/`. Put your project’s templates(ejs), scss, js, images files in it.

`sass/`, `js/`, `images/` files will compile and output to `build/`.

	rin/
	┣┳ templates/
	┃┣ sass/
	┃┣ js/
	┃┗ images/
	┃
	┣ index.html
	┃
	┗┳ build/
	 ┗┳ css/
	  ┣ js/
	  ┗ images/

# Templates

Rin supports [EJS](http://www.embeddedjs.com/) template. When you edit and save `.ejs` files under `templates/` directory, they will output as `.html` to root directory.

## Template tags

### site.json

Put variables which use for every pages.

Example:	
	
	{
	  "siteName": "Example Site"
	}

### index.ejs

If you want to use variables for particular single page, put variables into `<% var %>` at each page.

Example:
	
	<% var
	pageTitle = "Toppage";
	%>
	<head>
		<title><%= pageTitle %> - <%= siteName %></title>
	</head>

### Result
	
	<head>
		<title>Toppage - Example Site</title>
	</head>

# Images

Rin optimizes gif, jpg, png, svg images automatically using [gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin). Each files will output to `build/`.

# CSS

Rin supports scss.

	sass
	┣ style.scss // It imports under /lib files
	┗ lib
       ┣ _core.scss // Edit this files mostly
	   ┣ _button.scss // Buttons
	   ┣ _common.scss // Common components like `body` or `a` etc
	   ┣ _grid.scss // Responsive grid system
	   ┣ _normalize.scss // Normalize
       ┗ _variable.scss // Color variables

## _normalize.scss

 -> [normalize.css](http://necolas.github.io/normalize.css/)

## _grid.scss

It helps you make simple grid system. Like this:

### 3-column

    <div class="l-container">
      <div class="l-row">
        <div class="l-span4">
          Column A
        </div>
        <div class="l-span4">
          Column B
        </div>
        <div class="l-span4">
          Column C
        </div>
      </div>
    </div>

### 2-column

    <div class="l-container">
      <div class="l-row">
        <div class="l-span6">
          Column A
        </div>
        <div class="l-span6">
          Column B
        </div>
      </div>
    </div>

## _button.scss

Example:

    <a class="btn">Normal button</a>
    <a class="btn btn-light">Light color button</a>
    <a class="btn btn-primary">Primary button!</a>
    <a class="btn btn-large">Large button!!</a>

## _variable.scss

Color variables and breakpoints of browser window width.

### Media queries breakpoints

- `mq-lg`
    - Large display (>1240px)
- `mq-md`
    - Tablet display (<1024px)
- `mq-sm`
    - Small tablet & Smartphone (<767px)
- `mq-xs`
    - Smartphone (<480px)

#### Example:

    header h1 {
        font-size: 200%;
        @media #{$mq-lg} {
            font-size: 300%;
        }
        @media #{$mq-sm} {
            font-size: 100%;
        }
        @media #{$mq-xs} {
            font-size: 80%;
        }
    }

### at2x

Variables for retina devices.

- `at2x`
    - All retina devices
- `at2x-tablet`
    - Retina devices (larger than iPad display)
- `at2x-pc`
    - Retina devices larger than PC display (1025px)
    - Use this variables when you need to load too large file size images.

#### Example:

    header h1 {
        background: url("images/title.png");
        @media #{$at2x} {
            background: url("images/title@2x.png");
        }
    }

# JS

js files under `js/` will output to `build/js/scripts.js` with concatenated and compressed.

# Local Server

Rin runs local server by using [BrowserSync](http://www.browsersync.io/). Its default URL is <http://localhost:3000/>. It reloads your browser automatically when you update a file that gulp is watching.

# Author

### mactkg

Student from Tokyo.

- <http://makerbox.net/>
- Twitter: [@mactkg](http://twitter.com/mactkg/)

### Showkaku Sano (sanographix)

Graphic designer from Kyoto.

- <http://www.sanographix.net/>
- Twitter: [@sanographix](http://twitter.com/sanographix/)

# License

### Major components:

* Rin4: MIT license
* jQuery: MIT/GPL license
* Normalize.css: Public Domain
* html5shiv: MIT/GPL license
* gulp: MIT license
