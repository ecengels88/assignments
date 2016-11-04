# Form Practice Adonis

## Description

We've now introduced two different templating languages: Vue and Nunjucks.
We've also looked at client-side and server-side form submitting.
This is the Adonis Version.

### Learning Objectives

After completing this assignment, you should be able to:

* Use Adonis `Route.get` and `Route.post` to map routes to generator functions
* Use `node-fetch` with `yield` functions to wait for async actions
* Use Nunjucks templating including `if` and `for` statements and loops

### Review Objectives

After completing this assignment, you should be able to effectively use:

* Read and use CSS framework documentation (Bulma)
* Write logical HTML

## Details

### Deliverables

* A Adonis project (created using `adonis new`)
Recreate the following mockup form using data from `http://json-data.herokuapp.com/forms` along with Nunjucks templating.

![Screen Shot 2016-11-03 at 7.59.54 AM.png](https://tiy-learn-content.s3.amazonaws.com/f694e68e-Screen%20Shot%202016-11-03%20at%207.59.54%20AM.png)

This page should show up on the home/index page of your server (replacing the existing `welcome` page).

#### After Posting

The form should post and then show the user input (using the request object to grab inputs) in a table.

## Resources

* [Bulma Documentation](http://bulma.io/documentation/overview/start/)
* [Form Data](http://json-data.herokuapp.com/forms)
* Adonis Docs
  - [Templating](http://www.adonisjs.com/docs/3.1/templating)
  - [Request and Input](http://www.adonisjs.com/docs/3.1/request)
  - [Routing](http://www.adonisjs.com/docs/3.1/routing)

## Tasks

```md
* [ ] Create a new project named `19-template-practice-adonis` using the `adonis new` command
* [ ] Run `hub create` to create a new repository on Github
* [ ] Use `yarn` to add the `node-fetch` library
* [ ] Commit this as the "starting code"
* [ ] Push `master` branch
* [ ] Create `develop` branch
* [ ] **Checkpoint:** Setup a home view
  * [ ] Make a route that responds to get requests to `/`
  * [ ] Respond with a view (set up this view with an `.njk` file)
* [ ] **Checkpoint:** Setup Bulma
  * [ ] In the new view add a link to bulma using the CDN link listed on Bulma's website
* [ ] **Checkpoint:** Static Form HTML
  - [ ] Using the Bulma documentation as a guide, recreate the HTML for the form
    * [ ] Panel
    * [ ] Panel Heading
    * [ ] Panel Block with form
      - [ ] inputs, selects, and textareas
    * [ ] Panel Block with button
* [ ] **Checkpoint:** Setup Application Data and Startup
  - [ ] Add a variable called `apiUrl` in the get route and set it to: `http://json-data.herokuapp.com/forms`
  - [ ] Use `node-fetch` to fetch from the `apiUrl` using `yield` instead of `.then` chaining
  - [ ] Send results from the fetch into the view
* [ ] **Checkpoint:** Update the application template to loop through data fetched
  - [ ] Show type `select`s with their options, ids, and names
  - [ ] Show type textareas with their ids, icons, and names
  - [ ] Show type text/tel with their ids, icons, and names
* [ ] **Checkpoint:** Handle form submit
  - [ ] Make a post route for `/`
  - [ ] Get user inputs from the form from the request
  - [ ] Send this input to a view
* [ ] **Checkpoint:** Show input data in a form
  - [ ] In a new view add bulma cdn link
  - [ ] Create table with values from user input
```
