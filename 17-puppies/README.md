# Puppy Adoption

## Description

Now that we have routing, let's create a full CRUD (Create, Read, Update, Destroy) app with multiple pages/routes.

### Learning Objectives

After completing this assignment, you should be able to:

* Use Vue Router to create an application view/controller
* Use Vue Router to create dynamic routes
* Use Vue's `$emit` to "bubble up" events to the application controller
* Use object spread, array spread, and array functions (`filter` and `map`) to update array data
* Read and use CSS framework documentation (Bulma)

### Review Objectives

After completing this assignment, you should be able to effectively use:

* Use Vue.js to show data
* Use Vue.js to respond to user events
* Make Post Requests using `fetch`
* Style using SCSS

## Details

### Deliverables

* A project created using the Yeoman Qunit Broccoli Generator `yo qunit-broccoli` that uses Vue.js for rendering and event management
* Bulma with some extra configuration to style the application
* Information should store data to the server: `https://tiy-tn-class-api-fall-16.herokuapp.com/puppies/<your-name>`

Recreate the following application with all of following routes:

# Index (Home) Route

<!-- Image Here -->

This route should list a table of all puppies that have been entered in the system.
The table should:

* Show the puppy name
* Show the puppy age
* Show a link to "read more" which links to the detail route for the current puppy in the table

# New Route

<!-- Image Here -->

This route should be a form to create a new puppy with the following inputs:

* Name (`name` on the server)
* Age (`age` on the server)
* Sex (Ideally a drop down with "male" and "female") (`sex` on the server)
* Color (`color` on the server)
* Breed (`breed` on the server)
* Image Url (`image_url` on the server)
* Description (Use a `textarea`) (`description` on the server)

# Detail Route

<!-- Image Here -->

This route should show the details for a single puppy based on a dynamic `id` segment in the url.

This route should show:

* A title with the puppy name and a button
  - If the puppy is adopted show a green button with a paw and the words "I'm Adopted"
  - If the puppy is no adopted show a green button with a paw and the words "Adopt Me!"
    * When the user clicks on this blue button, update the current puppy with `adopted` set to `true` (probably want to `$emit` this)
* A picture of the puppy based on the `image_url` value of the puppy
* A row of information about the puppy:
  - Age
  - Breed
  - Color
  - Sex
* An "About Me" section showing the puppy `description`

### Requirements

## Resources

* [Bulma Documentation](http://bulma.io/documentation/overview/start/)
* Vue Docs
  - [Templating](http://vuejs.org/guide/syntax.html)
  - [Conditionals](http://vuejs.org/guide/conditional.html)
  - [Lists `v-for`](http://vuejs.org/guide/list.html)
  - [Events](http://vuejs.org/guide/events.html)
  - [Forms](http://vuejs.org/guide/forms.html)
* [Vue Router Docs](http://router.vuejs.org/en/index.html)

## Tasks

```md
* [ ] Create a new project named `17-puppy-adoption` using the `yo qunit-broccoli` command
* [ ] Run `hub create` to create a new repository on Github
* [ ] Push `master` branch
* [ ] Create `develop` branch
* [ ] **Checkpoint:** Setup Build Tools and Dev Tools
  - [ ] Use the setup npm script to install Vue, Vueify, and Vue Router
  - [ ] Uncomment the `vueify` lines from the `Brocfile.js` to enable Vueification (is that a thing?)
  - [ ] Uncomment the `app.use` code in `server/index.js` to support client-side routing for the dev server
  - [ ] Uncomment the plugins in `.eslintrc.js` to support linting for `.vue` files
* [ ] **Checkpoint:** Add styling with Bulma
  - [ ] Use `yarn` to install `bulma`
  - [ ] In `app.scss`
    * [ ] Add a `blue` variable set to `hsl(217, 71%,  53%)`
    * [ ] Add a `primary` variable set to the `blue` variable
    * [ ] Uncomment the `fa-font-path`
    * [ ] Import `bulma/bulma` before the font-awesome import
    * [ ] Make `.nav` have a background using the `primary` variable
    * [ ] Within `.nav` select `a.nav-item` and make the color set to the `white-bis` color
    * [ ] Make an `is-brand` class selector with `font-size: 1.2rem` and `font-weight: normal` to use for the left side "Puppies" in the navbar
* [ ] **Checkpoint:** Setup Vue Router
  - [ ] Use the `vrouter` snippet to setup the Vue router in `index.js`
  - [ ] Create a `routes` directory in your `app` directory
  - [ ] Create a `application.vue` component in the `routes` directory and use the `template` snippet to fill it with the starting skeleton for a component
  - [ ] Create a `application.vue` component in the `routes` directory and use the `template` snippet to fill it with the starting skeleton for a component
* [ ] **Checkpoint:** Static HTML Application Component
  - [ ] Using the Bulma documentation as a guide, recreate the application "wrapping" component with:
    * [ ] Navbar
      - [ ] "Puppies" (`.is-brand`) should link to the `index` route
      - [ ] "All Puppies" should link to the `index` route
      - [ ] "Add Puppy" should link to the `new` route
    * [ ] Sidebar
      - [ ] List of puppies (don't worry about `v-for` yet...)
        - [ ] Puppy image
        - [ ] Puppy name
        - [ ] "read more" link to the `detail` route passing the parameter for the `id` of the current puppy
    * [ ] Main/Outlet Area
      - [ ] `router-view`
        * [ ] Pass down `puppies` value
        * [ ] Pass down `apiUrl` value
        * [ ] Listen for `add` and trigger `addPuppy`
        * [ ] Listen for `remove` and trigger `removePuppy`
        * [ ] Listen for `update` and trigger `updatePuppy`
* [ ] **Checkpoint:** Setup Application Data and Startup
  - [ ] Add a variable called `apiUrl` and set it to: `https://tiy-tn-class-api-fall-16.herokuapp.com/puppies/ryan` (you'll change `ryan` later)
  - [ ] Setup `data` properties:
    * [ ] `puppies` set to a blank array
    * [ ] `apiUrl` set to `apiUrl`
  - [ ] Add a `getData` function within `methods`
    - [ ] Fetch to `apiUrl`, parse the json, then set `puppies` based on the results from the API
  - [ ] Add blank functions to `methods`
    * [ ] `addPuppy`
    * [ ] `removePuppy`
    * [ ] `updatePuppy`
* [ ] **Checkpoint:** Update the application template to show sidebar with real data
  - [ ] Update sidebar to loop through puppies
  - [ ] Show individual puppy within the loop
    * [ ] Puppy image
    * [ ] Puppy name
    * [ ] Update `router-link` to link pass in the `puppy.id` as the `id` url parameter
* [ ] **Checkpoint:** Create the index template
  - [ ] Add `puppies` as an item in `props` for the component
  - [ ] Add a `router-link` to `new` so that you can go to the new form
  - [ ] Make a table head with:
    * [ ] Name
    * [ ] Age
    * [ ] Empty head
  - [ ] Make a repeating table row for each puppy in the `puppies` array and show:
    * [ ] Puppy Name
    * [ ] Puppy Age
    * [ ] A `router-link` to the `detail` route and pass the pass in the current puppy's `id` as the `id` url parameter
```
