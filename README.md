# API Assignment
In this project, we'll be creating two sub-projects that both use Bootstrap and API requests. The first is a random dog generator and the second is weather displaying application.

## Part 1 - Random Dog Generator

In the first part of this assignment, you'll add a button to your webpage that
when clicked, will cause a random dog image to display. You'll use the Dog API (https://dog.ceo/dog-api/) to get a random dog image URL.

#### 1A) Update your HTML

Lets start by creating a `<button>` and an empty `<img>` in the HTML. 

Make the button look like [a nice Bootstrap button](https://getbootstrap.com/docs/5.0/components/buttons/). 

Additionally, put both your button and image in a Bootstrap "card"
component. Read the Bootstarp documentation to figure out how to do this: https://getbootstrap.com/docs/5.0/components/card/

#### 1B) Handle Button Click

Now, lets make it so that when the button is clicked, a random dog image is displayed.

To get a random dog image URL, we'll make a GET request to this url: `https://dog.ceo/api/breeds/image/random`. The Dog API will then send us a response which will be
an object formatted like:
```
{ 
  "message": "https:\/\/images.dog.ceo\/breeds\/otterhound\/n02091635_1860.jpg",
  "status": "success"
}
```

We can see that the message field contains the random dog image! Grab that URL, then set
your image's source to be that URL.

Everytime you click the button, you should see a new random dog image appear!

## Part 2 - Weather App

In this part, you'll allow a user to enter the name of a city into a text input,
then press a button to submit. Your application will check the weather in that city,
then display the results to the user.

#### 2A) Update your HTML

Start off by creating a text input and a submit button in the weather app section of your
HTML. Make these look nice with Bootstrap (https://getbootstrap.com/docs/5.0/forms/overview/).

#### 2B) Handling Button Click

Now, when the submit button is pressed. Take the text entered into the input box
and make an API request to check the weather in that city.

This can be done using this weather API: https://github.com/robertoduessmann/weather-api

To check the weather in a city, make a GET request to `https://goweather.xyz/weather{city}`,
substituting `{city}` with the name of the city you want to check the weather in.  To account for cities with a space (New York), use `encodeURI()` on your url.

You'll receive a response object that looks like:
```
{
    "temperature": "17 °C",
    "wind": "9 km/h",
    "description": "Partly cloudy",
    "forecast": [
        { "day": "1", "temperature": "19 °C", "wind": "14 km/h" },
        { "day": "2", "temperature": "12 °C", "wind": " km/h"   },
        { "day": "3", "temperature": "7 °C",  "wind": " km/h"   }
    ]
}
```

Take the temperature, wind, and description from this response and display them
somewhere on the page. You'll want to create new HTML elements in `index.html` that
will store this information.

## Stretch goals

* Create a third sub-project with an API of your choosing. A large list of public
APIs is available here: https://github.com/public-apis/public-apis I'd recommend
using one that requires no authentication. Be warned: many of them are quite complicated
to use.

* For each project, put the content returned from the API in a Bootstrap carousel.
Everytime the user makes a new API request, add a new slide to the carousel. The user
should be able to look through the carousel to see the results of all their requests.
