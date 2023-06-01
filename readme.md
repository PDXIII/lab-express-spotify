# Browsing Spotify

## About This Project

### Building An ExpressJS App

That was our boot camp cohort’s homework of the weekend. For me it was the first time to write an [ExpressJS](https://expressjs.com) app from scratch. And it wasn’t actually from scratch. [Ironhack](https://www.ironhack.com) has given us very detailed [information](https://github.com/ironhack-labs/lab-express-spotify) about what they were expecting and how to achieve it. Spotify offers an [API](https://developer.spotify.com/web-api/) that allows to fetch data and songs, and basically, we had to built a search interface for it with the option to listen to some snippets.

Pretty cool 😃!

### Why Express?

The experienced frontend engineer might ask this. Totally fair! Usually, you would pick a frontend library like [React](https://reactjs.org), [Vue](https://vuejs.org) or something else. The reason was Ironhack’s curriculum. And from my perspective it makes perfectly sense to understand how to deliver static HTML from a server first before you start to learn what you can do dynamically in the browser. Also very important, is the knowledge about templating. And [HandlebarsJS](https://handlebarsjs.com) is a great library to begin learning because of its simplicity.

### The Process

That was fun! It took me around 5 hours to build it and understand what I was doing. If you have read in the original ReadMe.md you might have noticed that the necessary steps for the server were well described. Therefore, I haven’t had any issues and I could focus a bit on styling the front end.

Call me weird but I love CSS! And since we haven’t been allowed to use Javascript in the front end, that would have made much easier to change classes of elements, I had a nut to crack. My goal was it provide a submit and a reset button when the input field is focused.

I found the solution with the `:focus-within` pseudo class. [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within) provides a very nice documentation about it. Applied to a parent it is triggered when any child is focused.

```css
.home form .button-container {
  display: inline-flex;
  position: absolute;
  right: -10em; /* moved out of sight */
  opacity: 0; /* and invisible */
  transition: all 0.3s ease-in-out;
}

.home form:focus-within .button-container {
  /* a child is focused */
  right: -5em; /* moved in */
  opacity: 1; /* and visible */
}
```

I really like it! It’s simple, easy to understand, and has an elegant effect.

### The Result

You can see this application running live on [Stackblitz,](https://stackblitz.com/edit/stackblitz-starters-8a4eez?file=readme.md)

## Installation

1. clone this repository on to your local machine
2. ```npm i```
3. ```npm run dev```
4. open your browser on <http://localhost:3000/>

## Disclaimer

To make this application embeddable, I had to exclude ```.env``` from ```.gitignore```. Which can cause an issue, because it stores the applications Spotify credentials. Please, take in consideration to get your own [Spotify credentials.](https://developer.spotify.com/web-api/)
