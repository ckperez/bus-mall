#Lab Assignment 3/29  
##Goals:
-Display 3 image photos side by side  
-Receive clicks on images  
   *Track clicks  
      *total clicks  
      *clicks on each image  
      *times each image is displayed   
-Generate 3 new images on click  
-Use a constructor for objects that will hold the following properties for each image   
   *name  
   *file path  
   *times displayed   
   *times clicked    

--------------------------------------------

##Approach:
-I created an html file with three blank image tags. I assigned them a matching class of of possibleChoiceBox, and unique classes that I have not used yet. I did not include an src attribute, as my plan for the generation of random images involved setting the src attribute in app.js.   
-In app.js, I created a constructor:  
        ```function MakeImageObject(name, filePath) {
              this.name = name;
              this.filePath = filePath;
              this.timesDisplayed = 0;
              this.timesClicked = 0;
              this.myID = '';```    
-I then made 3 methods on the prototype of `MakeImageObject` to make an html id from the name, increment the times displayed property, and increment the times clicked property. Then, image objects are instantiated with the constructor. The methods were all a bit redundant, but also very clear. Also, all of these objects were pushed to an array (current length:20), then the method to make html ids was called on the entire array with a for loop.   
-A function then loops through an array of the three `<img>` tags, the src attribute's value is set to a random image from my array of image objects, and the matching id attribute is assigned to each. This function, `putRandomImagesOnDOM` adds images to the DOM and calls the times displayed incrementer method on each image put on the DOM.
-An event listener for `click` was added to the shared class of the three `<img>` tags, and the handler does as follows:   
  *Increments total clicks    
  *Determines which image object reveived the click and records the individual click/choice by calling the click-incrementing method.     
  *`console.log`s the click and display counts for each object.    
  **`console.log`s the total click count.
