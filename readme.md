
This repo contains resources to help you create a weather app that loads data from an API.

If you have never seen JavaScript code before, you may want to begin with FreeCodeCamp:
https://www.freecodecamp.org/

JavaScript Functions
====================

Code that is not in a function will only run once at the application load. Logic that you want to call more than once should be placed into a function. 

    function showWeather(zip) {
        // TODO: build url and make fetch call here
        
        console.log('showWeather called for zip code:', zip); 
        // the above line writes to the browsers debugger console, it does not appear on the page.
    }
    
You can invoke a function from just about anywhere in your JavaScript and even from event handlers defined in the HTML. For the weather app, you'll want to show the weather again each time the user enters a new location. You may want to trigger the function from both an ENTER key being pressed in the textbox or at the click of a button.

You could also define another function that loads the weather by a Latitude Longitude pair.

Run script only AFTER page load
===============================
By default, JavaScript begins running as it is downloaded.  This also means the page content may not be fully loaded. If you try to access an element to update its text before it is loaded, then you will see an error.

Delay code to run until page load with the onload event. See the following walkthrough step for help:
https://github.com/NexulAcademy/intro-html-css-js#step-13-defering-execution-until-html-is-loaded

Note: You can only use variables and functions declared above where they are called from.

Fetching data from an API
=========================

Your 'showWeather' function will need to call an external weather API to get the data. JavaScript offers a function to do just that, called 'fetch'. See the following documentation for how to use fetch.
https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch 

Fetch is based on JavaScript 'promises'. Normal JavaScript code is synchronous, meaning it runs one line before moving to the next line. While a line of code is executing the browser cannot respond to user input. The way to share processing cycles with the browser to respond to user input is with 'asynchronous' code. A Promise is the most basic way to write asynchronous code. The fetch() method itself is designed as an asynchronous Promise.

helpful conceptual video (fetches an image):  
https://www.youtube.com/watch?v=tc8DU14qX6I&vl=en

great video (fetching data, like you need to do):  
https://www.youtube.com/watch?v=uBR2wAvGces
just logs the data from the API to the console. You will need to use that data to place it on the page.


The then() method call after the fetch() call is code that will continue processing once the API call has completed and returned data back to your application. In the final then(), you can use the data from the API to update text elements on the page (see next section).

To make the API call, building the proper URL for fetch(), refer to the documentation for the weather API or book API (depends on app you are building) 

The Weather API
---------------

The official documentation:
https://openweathermap.org/current

You will need to register for an API key on their site. Then read their API documentation to learn how to build a proper url to pass into your fetch() call.  Example, using their sample API:

    fetch('https://api.openweathermap.org/data/2.5/weather?zip=94040,us&APPID=YOUR_KEY_HERE')
        .then(...);

You can use string concatenation to build the url, so that the hardcoded 94040 zipcode can be replaced with the user specified zip code.
https://masteringjs.io/tutorials/fundamentals/string-concat


Updating page elements
======================

Once you get data back from the API, the next step is to show relevant parts of that data on the page.

JavaScript getElementById() is used to grab an element on the page.
https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById 

Once you have an element stored in a variable, you can update the element with built-in properties of the element.
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

Once the app loads, you may want to let the user enter a new zip code and show the weather for that location. Use a normal HTML text input and button for the interface. 

You can respond to a button click using the following examples:
https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_onclick

TIP: read your input value and send it off to your custom showWeather function.

You can read a textbox input value using the following example:
https://www.w3schools.com/jsref/prop_text_value.asp

    var x = document.getElementById("myText").value;

Getting current user GPS location
==================================

When the app loads, you may want to ask the user for permission to query their current GPS location, if the browser/device supports it. You can read about how to do that with the following resource.
https://www.w3schools.com/html/tryit.asp?filename=tryhtml5_geolocation

Once you have a location, you'll want to pass the location into a new 'showWeather()' function that takes a GPS Lat/Long pair.

Further reading
===============

See the Nexul Academy JavaScript walkthrough for examples using some of the above (all but fetch).
https://github.com/NexulAcademy/intro-html-css-js  

Maybe you want a location search box (auto-complete) like on Google maps?  You can get it from google using their 'places' API.
https://developers.google.com/places/web-service/autocomplete
