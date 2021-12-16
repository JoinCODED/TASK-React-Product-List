### Frontend

Make your products list dynamic.

#### Data file

1. In `src`, create a file called `products.js`.
2. In this file, create an array called `products` with objects as elements. Every object should have a `name`, `price` and `image`.
3. Add two different products to your array.
4. Export your array and import it in `App.js`.

#### Product List

1. Add two products that you want to sell under the shop image. Every product should have a name, image and price.
2. Replace the hard-coded names, images and prices with the data from the array `data`.

#### Mapping

1. Map over your `products` array, return the JSX code that represents one item.
2. Save your new array in a variable called `productsList`.
3. Replace your items' JSX with `productsList`.
4. Check your website, everything should be exactly the same.

#### Testing

At this point, nothing should've changed. How can we know everything is working properly?

1. Add a new product to your `products` array in `products.js`. It should render on the screen.
2. Remove two products from your array, they should be removed from the screen. Don't forget to put them back.

Here's an **example** of what your website would look like.

![Cookieshop example](https://i.imgur.com/IxOcHpf.png)
