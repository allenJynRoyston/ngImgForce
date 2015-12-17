# acr-backstretch

### What Am I?!
An awesome cropping tool that resizes an upload image and resizes it to the dimensions that you want.  
For example, take a 1080x720 image and size it to just 50x50, or vice versa.  

Based off the excellent cropping tool by alexk111.  Find the original here.  
Find it here:  (https://github.com/alexk111/ngImgCrop "Title")

### Live Demo 
[Check it out](https://allenroyston.herokuapp.com/access/ng-img-force/index.html "Title")
  
## Install
<code>
NPM:
npm install ng-img-force

Bower:
bower install ngImgForce
</code>

Ensure you link it correctly in your HTML
  <script src="./js/ng-img-force.js"></script>
  <link rel='stylesheet' type="text/css" href="css/ng-img-force.css">
  
And add it as a module for your app:
  var app = angular.module('myApp', ['ngImgForce']);

And add this chunk of code in your controller to handle the image upload:

      $scope.myImage='';
      $scope.myCroppedImage='';

      var handleFileSelect=function(evt) {
        var file=evt.currentTarget.files[0];
        var reader = new FileReader();
        reader.onload = function (evt) {
          $scope.$apply(function($scope){
            $scope.myImage=evt.target.result;
          });
        };
        reader.readAsDataURL(file);
      };
      angular.element(document.querySelector('#fileInput')).on('change',handleFileSelect);






### Version
1.0.0

### Updates
 - None

### Dependencies
- jQuery  (not included)
- backstretch.js (included)

### NPM / Bower
<code>
npm install acr-backstretch --save-dev
</code>
<br>
<code>
bower install acr-backstretch --save
</code>

### Installation
Include backstrech after you've included jQuery:<br>
<code>
&lt;script src="./js/backstretch.min.js"&gt; &lt;script&gt;
</code>
<br>
Include the module in your scripts after AngularJS<br>
<code>
&lt;script src="./js/acr-backstretch.min.js"&gt; &lt;script&gt;
</code>

Add acrBackstretch in your apps dependencies.<br> 
<code>
var app = angular.module('myApp', ['acrBackstretch']);
</code>

### Usage
<code>
&lt;div ng-parallax pattern="myPattern" speed="0"&gt; &lt; /div&gt; 
</code>

### Parameters
fade: [numbers] in miliseconds (i.e. 1000 is 1 second)<br>
fillheight: [number] in pixels (i.e. 400 is 400px)




License
----

MIT - go nuts y'all.
