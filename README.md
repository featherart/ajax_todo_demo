Todo Code-along - WDI

The goal of this lab is to demonstrate basic single page app functionality in a Rails app with unobtrusive JavaScript.

Using the 'remote: true' option in form_for with js.erb files we can create a single page app with no messy ajax calls visible in our code. 

We start with a form in the index, then add the dynamically created form to create.html.erb, then factor out the form into a partial so that items created dynamically will be rendered using the same form as items already stored in the database.

We will then add delete functionality so that items can be deleted dynamically.

Steps:

1. create a new Rails app 
2. generate a ToDo model having two fields, item:string and completed:boolean
2. generate a Todos controller having 2 methods: index and create
3. rake db:migrate
4. create the main view: views/todos/index.html.erb
5. create a form inside a <div> in the view that has 1 field and one checkbox for 'item' and 'completed', with 'remote: true'
6. below that create a 2nd <div> for "todos"
7. iterate through the @todos in that <div>
8. make sure the model has all fields attr_accessor (Rails 3.2.14)
9. implement your controller methods: index should create a new @todo, return all @todos and redirect_to both html and json formats.
10. create should take a :todo object and redirect_to .js
11. implement create.js.erb so that the create controller method has a template to redirect_to! this template should look just like the contents of your "todos" <div>
12. note the repetition here! refactor to a partial (can add generated by partial vs/generated by create.js.erb)
13. now implement delete: add a destroy method to controller that takes the :id as a parameter and has a redirect_to destroy.js.erb
14. create the file views/todos/destroy.js.erb
15. add an attribute to your <li> tag, data-id, that dynamically parses the id of each todo item
16. add a delete link to the form partial that points to the delete method and uses remote: true
17. in the destroy.js.erb use JQuery to find the item by id# and remove() it
18. revel in your glory!
