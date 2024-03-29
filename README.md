### Tasks

1.  Clone the repo
2.  Add the following dependencies to the project

        1. `moment` - `https://momentjs.com/`
        2. `faker` - `https://github.com/marak/Faker.js/`

3.  Run the `yarn install or npm install` command to install all dependencies

    a. start the app using the following command `npx nodemon`

    b. make sure you can see a basic page load at the endpoint `http://localhost:3010/home`

4.  Add the following elements to the `index.html` page found under `src/views`

        - text input that captures the first name of the user
        - a submit button that will submit the form using ajax

5.  The above page should be loaded whenever the user goes to `http://localhost:3010/home`
6.  Once the user is on the page, they should be able to perform the following actions

    a. Fill in the name and allow them to submit the form. ( _The form should not submit unless the name field is filled in_ )

    b. When sending the data to the backend, send it by making an ajax post request to the following endpoint and passing the required parameters ( _the page should not reload_ )

        Endpoint : POST `http://localhost:3010/time/1564590117/search`
        POST BODY
        {
                name : John, <-- user input
        }

        - 1564590117 - indicates the current timestamp in unix format and should be dynamic for every request made
        - name - indicates the inputted name from the user

7.  Receive the **time** and **name** fields in the backend.
8.  Using the parameters received above generate a list of 5 items that looks like the following

- id : random number generated by faker
- email : generate a random email using the name of the user using faker
- image : generate a random avatar image using faker
- updated : format the timestamp received from the front end into the format `DD/MM/YYYY HH:mm`

```json
{
  "payload": [
    {
      "id": 42686,
      "email": "john31@yahoo.com",
      "image": "https://s3.amazonaws.com/uifaces/faces/twitter/bluefx_/128.jpg",
      "updated": "07/08/2019 15:07"
    },
    {
      "id": 17368,
      "email": "john95@hotmail.com",
      "image": "https://s3.amazonaws.com/uifaces/faces/twitter/sterlingrules/128.jpg",
      "updated": "07/08/2019 15:07"
    }
  ]
}
```

8.  Send the data back to the front end and display the image from the 2nd item on the screen as a circular image. Each time the form is submitted, the existing image should be cleared and the new image received should be displayed.

### Bonus Tasks

- Print the time on the screen and change the text colour to any random colour every 2.5 seconds.
- If the frontend makes a request to an endpoint other than the ones mentioned above, return a response with the `status code` 404 and an empty array
