# Recipes

## Introduction

![thai_style_chicken_noodle_soup_pieces_recipe_web](https://user-images.githubusercontent.com/23629340/38369283-ac1bda62-38e7-11e8-9c9b-d9df623f1bc3.jpg)

Project developed using MERN stack;

We've learned how to use Mongoose to create Schemas and then interact with our MongoDB database;

In the following exercise, we will practice how to implement this by creating awesome recipes.


### Iteration 1 - Recipe Schema

Create a `Recipe` model inside of the file `/models/Recipe.model.js`. The schema should have the following fields:

- **title** - Type `String`. It should be required and unique.
- **level** - Type `String`. Can be one of the following values: _Easy Peasy_ - _Amateur Chef_ - _UltraPro Chef_ (remember the `enum` validator :wink:).
- **ingredients** - Type `Array` of `String`s (represented as `[ String ]`).
- **cuisine** - Type `String`. Should be required.
- **dishType** - Type `String`. Possible values: _breakfast_, _main_course_, _soup_, _snack_, _drink_, _dessert_ or _other_.
- **image** - Type `String`. Default value: _"https://images.media-allrecipes.com/images/75131.jpg"_.
- **duration** - Type `Number`. The minimum value should be 0.
- **creator** - Type `String`.
- **created** - Type `Date`. By default, today.

### Iteration 2 - Create a recipe

In `index.js`, after the connection to the database has been established, you should add a new recipe document to the database by calling the [`Model.create`](https://mongoosejs.com/docs/api.html#model_Model.create) static, passing it the recipe details as an object. After inserting the recipe, you should `console.log` the `title` of the recipe.

You can use MongoDB Compass to double check that everything is working as intended.

**To run your code, remember you should use:**

```shell
$ node index.js
```

Tip: When you have successfully created a new recipe (you see it in the database using Compass tool), you might want to comment out this step. The reason for this is that next time when you run `$ node index.js`, it will try to create a new recipe with the same name and you will get an error in the terminal related to the *duplicate keys* - the title should be unique, and the dish with that title already exists in the database.

### Iteration 3 - Insert multiple recipes

We are importing an array of recipes form the `data.json` file. Using the [`Model.insertMany`](https://mongoosejs.com/docs/api.html#model_Model.insertMany) static, you should add the entire array to the database. After inserting the documents, print the title of each recipe to the console.

Tip: Follow the same tip as in the previous step.

### Iteration 4 - Update recipe

Now you should have six different recipes in the database, but there was a mistake in one of them. The **Rigatoni alla Genovese** does not take that long. You should update the `duration` field and set it to **100**. You might want to use the [`Model.findOneAndUpdate`](https://mongoosejs.com/docs/api.html#model_Model.findOneAndUpdate) static. After updating it, print a success message!

### Iteration 5 - Remove a recipe

Oh oh! The `Carrot Cake` is no longer available, so we need to remove it from the database. Using the [`Model.deleteOne`](https://mongoosejs.com/docs/api.html#model_Model.deleteOne) static, remove that recipe from the database and display a success message after doing it!


# Developers GitHub

- [Fabio Gomes](https://github.com/fabiolpgomes)

