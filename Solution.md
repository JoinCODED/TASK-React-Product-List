#### Cookies List
Let's add a list of cookies to our page right under the cookie shop image.

1. First I'll add a `<div>` tag to wrap the list of cookies, and another `<div>` to wrap our two `<div>` tags as a parent.

 ```jsx
  <div>
   <div>
     <h1 className="text">Cookies and Beyond</h1>
     <h4 className="text">Where cookie maniacs gather</h4>
     <img
      alt="cookie shop"
      src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
      className="shop-image"
     />
   </div>
   <div></div>
 </div>
 ```
2. Let's add our first cookie, a chocolate chip cookie. We'll give every cookie an image, name and price:

 ```jsx
<div>
  <img
    alt="chocolate chip cookie"
    src="https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg"
  />
  <p>Chocolate Chip Cookie</p>
  <p>10 KD</p>
</div>
  ```

3. Let's style it a bit by giving every image a height and width and centering the text. In our `App.css`, we'll add a new styling class for the cookie image and we'll apply `text` style to the name and price.

 ```css
.cookie-image: { 
    width: 200px;
    height: 200px;
};
 ```

4. Let's apply it on our cookie:

 ```jsx
<div>
  <img
    alt="chocolate chip cookie"
    src="https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg"
    className="cookie-image"
  />
  <p className="text">Chocolate Chip Cookie</p>
  <p className="text">10 KD</p>
</div>
 ```

5. Then we'll just copy and paste this block of code to display one more cookie:

 ```jsx
<div>
  <img
    alt="cute cookie"
    src="https://i.pinimg.com/originals/f6/3e/2a/f63e2a1cd0c7d3c0ab9cd277d3f32050.jpg"
    className="cookie-image"
  />
  <p className="text">Cute Cookie</p>
  <p className="text">8 KD</p>
</div>
 ```

6. But the design is awful. Let's fix it by styling the `div` tag that's wrapping all three cookies. In `App.css`:

 ```css
.list: {
    align-items: center;
    justify-content: center;
    display: flex;
  }
 ```
 
 And apply the styles:

 ```jsx
return (
  <div>
    <div>...</div>
    <div className="list">...</div>
  </div>
);
 ```

7. Also, for every cookie `div` we will add a margin to make some space between them.

 ```jsx
.cookie: { 
    margin: 20px;
}

 ``` 

 And apply the styles:

 ```jsx
return (
  <div>
    <div>...</div>
    <div className="list">
      <div className="cookie">...</div>
      <div className="cookie">...</div>
    </div>
  </div>
);
 ```

And there you have it! A beautifully designed cookie list page!

####  Data File

1. Since the cookies array represents our data, let's create a new array in its own file and import it. Create a `cookies.js` file inside the `src` folder.

2. To import this array we need to export it first:

 ```jsx
 const cookies = [
  {
    name: "Chocolate Chip Cookie",
    price: 10,
    image:
      "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever- 
  no-chilling-1.jpg",
  },
  {
    name: "Adorable Cookie",
    price: 15,
    image:
      "https://i.pinimg.com/originals/f6/3e/2a/f63e2a1cd0c7d3c0ab9cd277d3f32050.jpg",
  },
  {
    name: "Katakeet Cookie",
    price: 7,
    image:
      "https://imagesvc.meredithcorp.io/v3/mm/image? 
       url=https%3A%2F%2Fassets.marthastewart.com%2Fstyles%2Fwmax-750%2Fd34%2Feaster-chick- 
       egg-cookies-102921707%2Feaster-chick-egg-cookies-102921707_horiz.jpg%3Fitok%3DUBZfwNLI",
  },
  ];

  export default cookies;
 ```

3. Now in `App.js`, we can easily import it.
  
 ```jsx
 import cookies from "./cookies";
  ```


#### Mapping

1. We need to iterate over our `cookies` array and create a new array of the cookie data in JSX. What iteration method can we use to iterate over an array, modify it and save the modified elements in a new array? The answer is `.map()`. let's start with returning the name of the cookie only and render it in a `<p>` tag.

 ```jsx
function App(){
 const cookieList = cookies.map((cookie) => <p>{cookie.name}</p>);
  return (
    [...]
  )
}
 ```
2.  It worked! Now instead of just returning `cookie.name`, let's return the whole cookie section! 

 ```jsx
 const cookieList = cookiesData.map((cookie) => (
  <div className="cookie"}>
    <img className="cookie-image"} alt={cookie.name} src={cookie.image} />
    <p className="text">{cookie.name}</p>
    <p className="text">{cookie.price} KD</p>
  </div>
));
 ```

3. Let's remove the cookie items from the return and replace them with cookieList:

 ```jsx
<div className="list">{cookieList}</div>
 ```
