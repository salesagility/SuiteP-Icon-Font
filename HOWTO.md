# Requirements
<pre>
sudo npm install -g svgo
sudo npm install -g icon-font-generator
</pre>

# Icon creation process
Create a build folder

<pre>
mkdir /tmp/suitepicon/
</pre>

Add new uncleaned icons to the build folder 

Use inkscape
* remove any masks and clipping
* resize the icons to 1024x1024
* use svgo  to compress svgs

Use svgo to clean / compress the svgs:

<pre>
svgo -f /tmp/suitepicon/ -o src
</pre>

# Build Icon set

<pre>
icon-font-generator src/*svg -o suitepicon --mono --center -p suitepicon --csspath suitepicon/suitepicon-glyphs.scss --name suitepicon 
</pre>
