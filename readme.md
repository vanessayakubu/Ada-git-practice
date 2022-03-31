# Readme

### Project Brief

With a time frame of 7 days, I was asked to build a new full stack web application for ADA digital skills.

### Technologies used

- HTML5
- JavaScript (ES6)
- React
- Python 3
- Flask
- Marshmallow
- PostgreSQL
- SQLAlchemy
- Insomnia
- Git/GitHub
- Moment.js

## Overview

Users who are logged in can access more of the app's functionality including:

- Viewing their user profile
- Viewing ADA college's new Victoria campus
- Accessing photos and information of current apprentices
- Edit personal profile details, or delete their account

## Development process

The first step of the project was to plan the models and database structure.
Wire framing was made with pen and paper, before I used Trello to manage the project.

### BackEnd

The main Python framework used was Python-Flask, with SQLAlchemy utilised for database interaction.

Flask methods such as Blueprint were used to register routing logic to the application.

As data retrieved from the PostgreSQL database via SQLAlchemy were objects, the Flask Marshmallow library was used for serialising models into JSON strings. Marshmallow could then be used for validating schemas and formatting data such as timestamps.

Once the database was functional, models and routes were created. The first model created was the user. Once the CRUD routes and testing were working with requests made in Insomnia, I could move onto creating the frontend of the application using React.

### Frontend

The front end of the application required the use of several ternary operators, and several JavaScript ES6 features such as the spread operator, map and filter to extract data from the backend.

For styling the application, I used front end framework React Semantic UI. As it was my first time using this framework, I had to read the documentation provided by Semantic UI to implement the framework on forms, user comments and page layouts.

## Challenges

One of the biggest challenges in building this application involved directing information for users who were authenticated and those who were just browsing the site.

In the backend, the definition of the current user (the user logged in) was and saved by a flask object known as g.

```
        g.current_user = user
```

In the front end, this data could be accessed and used to define if the user id matched that of the user logged in.

```
getUser() {
  axios.get(`/api/users/${Auth.getPayload().sub}`)
    .then(res => {
      this.setState({ currentUser: res.data })
    })
}
```

As this was a solo project, the time frame given to complete the application - 7 days meant I had to recognize there was alot of functionality I still wanted to add.

## Future features

- Better error handling and validation for forms
- A messaging function between users
