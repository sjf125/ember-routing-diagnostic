# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Inside the Ember Application Router, you list all of the url routes that Ember will need to display (i.e. call upon the proper model).  In an Ember Route, you would put (or call from an API) all the data you want to display for a particular view.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Boston{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The top route displays only one product, while the bottom route could display the details of one product, while still showing the list of all products.

    Clicking a link from the index of all products would result in re-rendering of the whole page for the top route, but only for a small part of the page in the bottom route.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    [params.movie_id - 1]
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    HTMLbars:

    {{#each thing as |thinger|}}
      {{thinger.key}}
    {{/each}}
    ```
