# Guidance

## 1A)

* Add a `<button>`  and `<img>` element to your HTML file
* Give them each some unique ID that you can query them with in your JS later
* You can leave the `src` of your `img` blank for now

## 1B)

* In `main.js`, first query your button with `document.querySelector`
* Add an event listener to the button that runs a function when the button is clicked. To test it, just make this function log a message.
* Now, inside your event listener function, send an API request. To do this, use the built-in `fetch()` function as is seen below.

```javascript
fetch(URL)
    .then((data) => data.json())
    .then((response) => {

        // Handle the API response here.

        // You can access the response object via the `response` parameter

    })
    .catch((error) => console.log(error));
```

* When you handle the API response object, get the `.message` field from it and set the `src` of your `img` to be that value (it's a random dog image URL)

## 2A)

* Create a text input (`<input type="text">`) and a `<button>`
* Add unique IDs for each element to query them with later
* Bootstrap them up: https://getbootstrap.com/docs/5.0/forms/overview/
* Additionally, create three `div` elements that will store the temperature, wind, and description data fetched from the API

## 2B)

* Query the button with `document.querySelector`
* Add an event listener on the button that handles clicks
* In your event listener function...
  * Query the text input
  * Get the `.value` of the text input
  * Create a variable that holds the URL to which you'll make your GET request. It will look like this `https://goweather.herokuapp.com/weather/{city}` but with `{city}` replaced with the value of the text input
  * Make a GET request to that URL with `fetch` (syntax seen above)
  * When you handle the API response object
    * Individually query your `div`s for temperature, wind, and description
    * Store the `.temperature` proprety of the API response object in the temperature div. Do the same for `.wind` and `.description`
    
