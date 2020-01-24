
This repo contains resources to help you create a weather app that loads data from an API

Fetching data from an API
=========================

JavaScript, fetch() is used to make the call to the API url
https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch 

In the final then(), you can use the data from the API to update text elements on the page.
To make the API call, building the proper URL for fetch, refer to the documentation for the weather API or book API (depends on app you are building) 

helpful conceptual video (fetches an image):  
https://www.youtube.com/watch?v=tc8DU14qX6I&vl=en

great video (fetching data, like you need to do):  
https://www.youtube.com/watch?v=uBR2wAvGces
just logs the data from the API to the console. You will need to use that data to place it on the page.

TIP: You may want to wrap your fetch call in a custom function of your own, that takes a parameter of the zip code OR GPS location
to show weather for.

   function showWeather(zip) {
     // TODO: build url and make fetch call here
   }

Updating page elements
======================

JavaScript is also used to update the appropriate elements on the page.
select an element, getElementById()
https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById 

Update the  element with innerText or innerHtml or innerText
https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML  
OR
https://www.w3schools.com/jsref/prop_node_innertext.asp  

OR you can do the same with jQuery:
 select an element with a jQuery selector  
https://api.jquery.com/category/selectors/   
then update the selected elements content
https://api.jquery.com/html/ 
OR
https://api.jquery.com/text/  

Get value of an input textbox
==============================

Respond to a button click
https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_onclick

TIP: read your input value and send it off to your custom showWeather function.

reading a textbox input value
https://www.w3schools.com/jsref/prop_text_value.asp

var x = document.getElementById("myText").value;

Getting current user GPS location
==================================

https://www.w3schools.com/html/tryit.asp?filename=tryhtml5_geolocation

Further reading
===============

See our JavaScript walkthrough for examples using some of the above (all but fetch).
https://github.com/NexulAcademy/intro-html-css-js  
