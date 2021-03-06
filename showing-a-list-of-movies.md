# Showing A List of Movies

To populate the `list` component with a list of movies from `App`, the parent component, send a request to your server for the data.

## Fetch the Movies

To obtain a list of the movies:

1. Import `axios`, a library for making Ajax requests:

   ```javascript
   import axios from 'axios';
   ```

2. Add the Ajax logic to the `created` lifecycle method of the `App` component:

   ```javascript
   axios.get(this.url)
   .then(res => {
   this.movies = res.data;
   })
   ```

   The logic sends a `get` request with `axios` to a URL stored in `this.url`. When a payload returns, it sets `this.movies` to the value of the payload.

3. Define `movies` and `url` in the model:

   ```javascript
   data() {
   return {
   movie: {},
   movies: [],
   url: '<YOUR WEBTASK URL>/movies'
   };
    },
   ```

## Render `VideoList`

Now import the `VideoList` component and render its element.

1. Import `VideoList`:

   ```javascript
   import VideoList from './components/VideoList.vue';
   ```

2. Specify the child in the component:

   ```javascript
   components: {
   VideoPlayer,
   VideoList
   }
   ```

3. Render to the DOM immediately below the `VideoPlayer` component:

   ```markup
   <div class="container">
    <h2 class="is-size-3">Movies</h2>
    <VideoList movie="updatePlayer" :movies="movies"></VideoList>
   </div>
   ```

## Handle the Selected Videos

Afterwards, the `choose-movie` event calls the `updatePlayer` method if the event is triggered. Therefore, add `updatePlayer` to the `methods` object:

```javascript
  methods: {
  updatePlayer(movie) {
  this.movie = movie;
  },
  }
```

`updatePlayer` sets the value of `movie`, which triggers the watch in `VideoPlayer`, causing a change in the trailer that is playing.

So far, so good:

![](https://res.cloudinary.com/christekh/image/upload/v1521675173/Screen_Shot_2018-03-22_at_12.32.28_AM_pdjmtq.png)

You can also select a movie to see its trailer:

