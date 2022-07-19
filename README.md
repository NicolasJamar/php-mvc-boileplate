# php mvc boilerplate
This repo contains a very simple, very basic skelleton for MVC projects.

This is only meant for educational purposes, not to be used in real life projects!

## What is an MVC?

MVC is a classic web design pattern consistent of three levels, and is an extension of the principle of **separation of concerns**:

- **Models** are classes that contain data. They usually correspond to a table from your database.
- **Views** are files that will mostly contain HTML. Any user facing end result will be made here.
- **Controllers** are classes responsible to control the handling of a request: they will load the right models and provide them to the correct view.

In this template, you have 3 different directories:
- **Controller/**: has access to GET/POST vars, receives the Request
- **Model/**: The interactions with the database lives here. Your requests should be here, for example the Product and Customer class.
- **View/**: Your HTML files.

While splitting up the Controller & Model is quite intuitive, splitting up the View from the Controller might require a larger change in how you write code. Let us look at some example:

```php
<?php
//oldcode.php
if($_GET['age'] > 18) {
    echo '<h1>You are an adult!</h1>';
} else {
    echo '<h1>You are a child!</h1>';
}
```

We can split this up into two files:
```php
<?php
<!-- controller.php -->
$sentence = ($_GET['age'] > 18) ? 'You are an adult!' : 'You are a child!';
require 'view.php';
```

```php
<!-- view.php -->
<h1><?php echo $sentence?></h1>
```
