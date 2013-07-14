<h3><em>Update: I am currently improving JResponsive so that it can support different width and height for different divs</em></h3>

<h3><em><span>If you don't want to create content_array manually. You can let Jresponsive take care of that for you by not defining content_array property.</span></em></h3>
<pre>$("#container_id").jresponsive({
  <a>transormation</a>: 'animation', 
  <a>min_size</a>: 100,
  <a>max_size</a>: 250,
  <a>height</a>:250,
  <a>hspace</a>:10,
  <a>vspace</a>:10,
  <a>class_name</a>: 'item',
  <strike><a>content_array</a>: content</strike>
});</pre>
<a>Note: Make sure when you struture your html from the beginning, follow the pattern:</a>
<code>
< div id="container_id">
	< div class="class_name"></ div>
	< div class="class_name"></ div>
	< div class="class_name"></ div>
	.......
</ div>
</code>


<h3><em><span>Create divs first inside the container then push them all into the array passed to JResponsive:</span></em></h3>
<pre style="color:#62C2CC">
var array = [];
array = $('#container .content').map(function(){
    return $(this).html();          
});
$('#container').empty();
var length = array.length;
for(var i = 0; i ' + array[i] + '';           
};
</pre>

<h3><em>JResponsive now will resize images inside the container automatically based on the initial propotion of the container width and the image width. </em></h3>
<h4><em>JResponsive now supports callback function as below</em></h4>
<pre style="color:#62C2CC">
$("div").jresponsive({
  .......
},callback);
function callback(){
  ......
}
</pre>
<h1><strong>Introduction notes</strong></h1>
JResponsive will organize your content in an efficient, dynamic and responsive layout. It can be applied to a container element and it will arrange its children in a layout that makes optimal use of screen space, by "packing" them in tightly. One of the very famous website that using this type of layout is <a href="http://www.pulse.me">Pulse.</a>
<h1><strong>Simplicity is the ultimate sophistication</strong></h1>
A simple jQuery plugin that allows you to add a dynamically-resized layout to any page or element, customize the layout the way you want with or without top,right,left or bottom navigations.
<h3>Usage is simple!</h3>
<p>Just include this script after jQuery. Requires jQuery 1.5+. Use
					<code>$('...').jresponsive({...})</code>
					instead of jQuery's
					<code>$('...').animate.</code>
					It has the same syntax as animate.
</p>
<pre>$("div").jresponsive({
  <a>transormation</a>: 'animation', 
  <a>min_size</a>: 100,
  <a>max_size</a>: 250,
  <a>height</a>:250,
  <a>hspace</a>:10,
  <a>vspace</a>:10,
  <a>class_name</a>: 'item',
  <a>content_array</a>: content
});</pre>
<h3>JResponsive provides the following transformations for use with</h3>
<code>transfromation</code><strong>property</strong>
<p><strong>animation</strong>
<small>transition</small></p>
<p><strong>fade</strong>
<small>fade in and out</small></p>
<h1>Supported browsers</h1>
<p>	JResponsive works well with all of the current modern browsers. JResponsive uses <code>JQUERY library</code>.	</p>
<ul class="supported-browsers">
  <li>IE 8+</li>
  <li>Firefox 4+</li>
  <li>Safari 5+</li>
  <li>Chrome 10+</li>
  <li>Opera 11+</li>
  <li>Android browser</li>
</ul>
<h3>If any issues found</h3>
<p>If for any reason, you need JResponsive to be supported for older versions of any browsers in the list, please let me know i will try as hard as i can to make it work.</p>
<h1>Recipes</h1>
<h2>Example setting</h2>
<p>JResponsive is a JQuery plugin which means you can use id $('#grid').JResponsive({..}) or class $('.grid').JResponsive({..}) as reference.</p>
<pre>$('#grid').JResponsive({
 	    transfromation: 'default',
			min_size: 100,
			max_size: 250,
			height:	250,
			nav_name: '#navigation',
			class_name: 'item',
			content_array: content,
});</pre>
<h2>transformation</h2>
<p>Define custom transformation through transfromation property. JResponsive currently supports 2 custom transformation transfromation: 'animate' transfromation: 'fade'</p>
<pre>
$('#grid').JResponsive({
  		transformation: '',
});
</pre>
<h2>min-size</h2>
<p>This is the minimun width of each of the element that it is allowed to shrink, because when window width changed, it depends on how much it changes elements will change the width or change position to fit the container. min-size: 100</p>
<pre>
$('#grid').JResponsive({
      min-size: 100,
});
</pre>
<h2>max-size</h2>
<p>The maximun width of each of the element that it is allowed to reach. Based on this property, JResponsive will calculate how many elements will fit the container. max-size: 300</p>
<pre>
$('#grid').JResponsive({
      max-size: 250,
});
</pre>
<h2>height</h2>
<p>This is the height of each element inside the container. If set as 0, the height will be always equal the width of the element. height: 0</p>
<pre>
$('#grid').JResponsive({
      height: 200,
});
</pre>
<h2>hspace</h2>
<p>Horizontal gap between elements</p>
<pre>
$('#grid').JResponsive({
      hspace: 40,
});
</pre>
<h2>vspace</h2>
<p>Vertical gap between elements</p>
<pre>
$('#grid').JResponsive({
      vspace: 40,
});
</pre>
<h2>item-name</h2>
<p>The class name of each of the element inside the container div. This will give users total control over the design of the layout. You can use class: item-name: '.item' or id item-name: '#item'</p>
<pre>
$('#grid').JResponsive({
      item-name: '.item',
});
</pre>
<h2>content_array</h2>
<p>This is where user will pass an array containing all of the elements that will be stored inside the container div. Each of the array element will become an item positioned inside the container div. Users can use any html tag for each of the element. Build the array from any source before passing it to JResponsive. content_array: content</p>
<pre>
var content = [];
content[0] = '&lt;div class="item-bg">&lt;div class="bg-color">&lt;/div>&lt;div class="item-info">&lt;div class="title">Kyocera Revolution Series 7-Inch Serrated Slicing Bread Knife&lt;/div>&lt;div class="price">$34.95&lt;/div>&lt;/div>&lt;/div>';
content[1] = '&lt;div class="item-bg">&lt;div class="bg-color">&lt;/div>&lt;div class="item-info">&lt;div class="title">Kyocera Revolution Series 7-Inch Serrated Slicing Bread Knife&lt;/div>&lt;div class="price">$34.95&lt;/div>&lt;/div>&lt;/div>';
$('#grid').JResponsive({
		  content_array: content,
});
</pre>


<h4><strong>Go to the <a target"_blank" href="http://www.jresponsive.is-great.net"> main website</a> to see how it works and more information, specially check out the interactive example</strong></h4>
