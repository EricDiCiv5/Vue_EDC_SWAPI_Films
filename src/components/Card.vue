<template>
  <main>
    <Loader v-if="!pelis.length" />
    <div v-else id="allFilms">
      <h2>All films</h2>
      <article v-for="(pelicula, index) in pelis[0]" :key="pelicula">
        <h4>
          {{ pelicula.title }}
        </h4>
        <section id="firstOne">
          <figure>
            <img :src="buildPath(photo_Url, index)" :alt="pelicula.title" />
          </figure>
          <p>{{ pelicula.opening_crawl }}</p>
        </section>
        <section id="secondOne">
          <div id="directorYear">
            <p>Director: {{ pelicula.director }}</p>
            <p>Release Year: {{ pelicula.release_date.split("-")[0] }}</p>
          </div>
          <div id="stats">
            <h5>In this movie appears:</h5>
            <ul>
              <li>{{ pelicula.characters.length }} characters</li>
              <li>{{ pelicula.planets.length }} planets</li>
              <li>{{ pelicula.starships.length }} spaceships</li>
              <li>{{ pelicula.vehicles.length }} vehicles</li>
              <li>{{ pelicula.species.length }} species</li>
            </ul>
          </div>
        </section>
      </article>
    </div>
  </main>
</template>

<script setup>
import Loader from "./Loader.vue";

defineProps({
  pelis: {
    type: Array,
    default: () => [],
    required: true,
  },
});
const buildPath = (photoPath, num) => {
  return "" + photoPath + "" + (num + 1).toString() + ".jpg";
};
const photo_Url = "https://starwars-visualguide.com/assets/img/films/";
</script>

<style scoped>
main {
  height: auto;
}

main h2 {
  font-family: "StarWars2";
  text-align: center;
  font-size: 3vw;
  color: #c9b823;
  margin-top: 5vh;
}

#allFilms {
  margin: auto;
  width: 85%;
}

#allFilms > article {
  background-color: rgba(153, 153, 153, 0.6);
  border-radius: 20px;
  box-shadow: 0px 0px 20px rgb(110, 122, 156);
  margin: 3% auto;
  display: flex;
  flex-flow: column wrap;
  justify-content: space-evenly;
  align-items: center;
}

#allFilms > article > #firstOne {
  flex: 1;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  align-items: center;
}

#allFilms > article > h4 {
  text-align: center;
  align-self: flex-start;
  margin: 3vh auto;
  padding-bottom: 1vh;
  font-family: "StarWars";
  letter-spacing: 3px;
  font-size: 2vw;
}

#allFilms > article > #firstOne > figure {
  display: inline-block;
}

#allFilms > article > #firstOne > p {
  display: inline-block;
  text-align: justify;
  font-family: "Space Grotesk";
  font-size: 1.5vw;
  line-height: 2.5;
  width: 60%;
  color: #c9b823;
  text-shadow: 0px 3px 10px #000;
}

#allFilms > article > #secondOne {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  align-items: flex-start;
  border-radius: 25px;
  width: 100%;
  padding: 1%;
}

#allFilms > article > #secondOne > #directorYear {
  margin-left: 8.5%;
  line-height: 2.5;
  text-align: center;
  font-family: "StarWars";
  text-shadow: 0px 0px 30px rgb(101, 117, 163);
}

#allFilms > article > #secondOne > #stats {
  background-color: rgba(170, 170, 170, 0.4);
  box-shadow: 0px 0px 7px #dbd498;
  padding: 1.5%;
  margin-right: 5%;
}

#allFilms > article > #secondOne > #stats > h5 {
  flex: 1;
  text-align: center;
  font-family: "Space Grotesk";
  font-size: 1.5vw;
  padding-bottom: 3vh;
}

#allFilms > article > #secondOne > #stats > ul {
  flex: 2;
  list-style-type: square;
}

#allFilms > article > #secondOne > #stats > ul > li {
  margin: auto 4vw;
  font-size: 1.1vw;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}

@media screen and (max-width: 800px) {
  main h2 {
    font-size: 4vw;
    color: #c9b823;
    margin-top: 5vh;
  }

  #allFilms > article > h4 {
    font-size: 3vw;
    margin: 4.5vh auto;
  }

  #allFilms > article > #firstOne > figure {
    display: block;
    width: 75%;
  }

  #allFilms > article > #firstOne > figure > img {
    width: 100%;
  }

  #allFilms > article > #firstOne > p {
    font-size: 2vw;
    line-height: 3;
    width: 75%;
  }

  #allFilms > article > #secondOne > #stats {
    background-color: rgba(170, 170, 170, 0.4);
    box-shadow: 0px 0px 7px #dbd498;
    padding: 1.5%;
    margin-right: 5%;
  }

  #allFilms > article > #secondOne > #stats > h5 {
    font-size: 2.5vw;
    padding-bottom: 3vh;
  }

  #allFilms > article > #secondOne > #stats > ul {
    list-style-type: square;
  }

  #allFilms > article > #secondOne > #stats > ul > li {
    margin: auto 4vw;
    font-size: 1.6vw;
  }

  #allFilms > article > #secondOne {
    border-radius: 25px;
    width: 100%;
    padding: 1%;
    margin: 4vh auto;
  }
}

@media screen and (max-width: 420px) {
  main h2 {
    font-size: 5vw;
    color: #c9b823;
    margin: 4vh auto 3.5vh;
  }

  #allFilms {
    margin: auto;
    width: 80%;
  }

  #allFilms > article > h4 {
    font-size: 4.5vw;
    margin: 3.5vh auto;
  }

  #allFilms > article > #firstOne > figure {
    display: block;
    width: 85%;
  }

  #allFilms > article > #firstOne > figure > img {
    width: 100%;
  }

  #allFilms > article > #firstOne > p {
    font-size: 3vw;
    line-height: 3.5;
    width: 85%;
  }

  #allFilms > article > #secondOne {
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
    align-items: center;
    border-radius: 25px;
    width: 100%;
    padding: 1%;
    margin: 2vh auto;
  }

  #allFilms > article > #secondOne > #directorYear {
    margin: 1vh auto 3.5vh;
    line-height: 2.5;
  }

  #allFilms > article > #secondOne > #stats {
    padding: 3.5%;
    margin: auto;
  }

  #allFilms > article > #secondOne > #stats > h5 {
    font-size: 3.5vw;
    padding-bottom: 3vh;
  }

  #allFilms > article > #secondOne > #stats > ul {
    list-style-type: square;
  }

  #allFilms > article > #secondOne > #stats > ul > li {
    margin: auto 4vw;
    font-size: 3.2vw;
  }

  #allFilms > article > #secondOne {
    border-radius: 25px;
    width: 100%;
    padding: 1%;
    margin: 4vh auto;
  }
}
</style>
