<template>
  <header
    :style="{
      background: 'url(' + movie.Poster + ')',
      backgroundSize: 'cover',
      backgroundPosition: 'center',
    }"
  >
    <div id="content">
      <img id="poster" :src="movie.Poster" alt="placeholder" />

      <div id="random-content">
        <h2 id="title">{{ movie.Title }} ({{ movie.Year }})</h2>

        <p id="released-runtime-wrapper">
          <span id="released"
            ><strong>{{ movie.Released }}</strong></span
          >
          &bull;
          <span id="runtime">{{ movie.Runtime }}</span>
        </p>

        <p id="genre">{{ movie.Genre }}</p>

        <p id="director-wrapper">
          <strong>Directed by: </strong>
          <span id="director">{{ movie.Director }}</span>
        </p>
        <p id="actors">{{ movie.Actors }}</p>

        <p id="plot">{{ movie.Plot }}...</p>

        <p id="imdb-wrapper">
          <strong>IMDb: </strong
          ><span id="imdb-rating">{{ movie.imdbRating }}/10</span>
        </p>

        <p v-for="item in movie.Ratings" :key="item.Source">
          <strong>{{ item.Source }}: </strong><span>{{ item.Value }}</span>
        </p>

        <RandomButton id="random-button" />
      </div>
    </div>
  </header>
</template>

<script>
import RandomButton from "./RandomButton.vue";

export default {
  name: "Random",
  components: { RandomButton },
  props: {
    movie: {
      default() {
        return {
          Title: "Last Night in Soho",
          Year: "2021",
          Rated: "R",
          Released: "29 Oct 2021",
          Runtime: "116 min",
          Genre: "Drama, Horror, Mystery",
          Director: "Edgar Wright",
          Writer: "Edgar Wright, Krysty Wilson-Cairns",
          Actors: "Thomasin McKenzie, Anya Taylor-Joy, Matt Smith",
          Plot: "An aspiring fashion designer is mysteriously able to enter the 1960s where she encounters a dazzling wannabe singer. But the glamour is not all it appears to be and the dreams of the past start to crack and splinter into something da",
          Language: "English",
          Country: "United Kingdom",
          Awards: "1 win & 1 nomination",
          Poster:
            "https://m.media-amazon.com/images/M/MV5BZjgwZDIwY2MtNGZlNy00NGRlLWFmNTgtOTBkZThjMDUwMGJhXkEyXkFqcGdeQXVyMTEyMjM2NDc2._V1_SX300.jpg",
          Ratings: [
            {
              Source: "Internet Movie Database",
              Value: "7.3/10",
            },
            {
              Source: "Metacritic",
              Value: "67/100",
            },
          ],
          Metascore: "67",
          imdbRating: "7.3",
          imdbVotes: "1,275",
          imdbID: "tt9639470",
          Type: "movie",
          DVD: "N/A",
          BoxOffice: "N/A",
          Production: "N/A",
          Website: "N/A",
          Response: "True",
        };
      },
      type: Object,
    },
  },
};
</script>

<style scoped>
header {
  position: relative;
}

#poster {
  justify-self: center;
  height: 600px;
}

#content {
  display: grid;
  grid-template-columns: min-content 1fr;
  column-gap: 4rem;

  padding: 4rem 10rem;

  backdrop-filter: blur(1rem) brightness(0.5);

  color: white;

  z-index: 1;
}

#content p {
  margin: 8px 0 0 0;
}

#content #title {
  margin: 0;
}

#content #released-runtime-wrapper {
  margin-top: 24px;
}

#content #director-wrapper,
#content #plot,
#content #imdb-wrapper,
#content #random-button {
  margin-top: 40px;
}

@media screen and (max-width: 599px) {
  header {
    grid-template-columns: 1fr;
  }
}
</style>
