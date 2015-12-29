# ng-img-force

### What Am I?!
An awesome cropping tool that resizes an upload image and resizes it to the dimensions that you want.  
For example, take a 1080x720 image and size it to just 50x50, or vice versa.  

Based off the excellent cropping tool by alexk111.
[Find it here](https://github.com/alexk111/ngImgCrop)

### Live Demo 
[Check it out](https://allenroyston.herokuapp.com/access/ng-img-force/index.html)
  
## Install
NPM:
<code>npm install ng-img-force</code>
<br>
Bower:
<code>bower install ngImgForce</code>



Ensure you link it correctly in your HTML<br>
```
<script src="./js/ng-img-force.js"></script>
<link rel='stylesheet' type="text/css" href="css/ng-img-force.css"></link>
```
  
  
  
And add it as a module for your app:<br>
```
var app = angular.module('myApp', ['ngImgForce']);
```




And add this chunk of code in your controller to handle the image conversion:
```
app.controller('testController', ['$scope', function($scope) {
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
}])
```

Then add this to your page.  You'll need at least the input and the img-force (preview is for funsies)
```
<!-- FOR UPLOADING -->
<input id="fileInput" type="file" />

<!-- FOR CROPPER -->
<img-force   image="myImage"
             result-image="myCroppedImage"
             area-min-size="100"
             result-image-size='{w: 200, h: 200}'>
</img-force>
 
 
 
<!-- PREVIEW -->
<img  ng-src="{{myCroppedImage}}" />

```


### Parameters
result-image-size: [object] -> {w: [number], h: [number]}

area-min-size:     "100" is the default.  If image cropper doesn't fit correctly adjust this to at least be close to your width.  





### Version
1.0.0

### Updates
 - None

### Dependencies
- None, just Angular 1.4+




License
----

MIT - go nuts y'all.
