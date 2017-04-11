# Requirements

sudo npm install -g svgo
sudo npm install -g icon-font-generator

# Icon creation process
Create a build folder

<pre>
mkdir /tmp/suitepicon/
</pre>

Add new uncleaned icons to the build folder 

Use inkscape
* remove any masks and clipping
* resize the icons to 1024x1024
* use svg o 

Use svgo to clean / compress the svgs:

svgo -f /tmp/suitepicon/ -o src
 

# Build Icon set
icon-font-generator --name suitepicon src/*svg -o suitepicon --mono --center

in the suitepicon.css
rename the i class and the .icons- classes to suitepicon

example
<pre>
@font-face {
    font-family: "suitepicon";
    src: url("./suitepicon.eot?c23135768b32b403bdac5db1976d616a?#iefix") format("embedded-opentype"),
url("./suitepicon.woff?c23135768b32b403bdac5db1976d616a") format("woff"),
url("./suitepicon.ttf?c23135768b32b403bdac5db1976d616a") format("truetype"),
url("./suitepicon.svg?c23135768b32b403bdac5db1976d616a#suitepicon") format("svg");
}

.suitepicon {
    line-height: 1;
}

.suiteicon:before {
    font-family: suitepicon !important;
    font-style: normal;
    font-weight: normal !important;
    vertical-align: top;
}

.suitepicon-module-documents:before {
    content: "\f101";
}

</pre>

copy the contents of suitepicon to suitep.sass