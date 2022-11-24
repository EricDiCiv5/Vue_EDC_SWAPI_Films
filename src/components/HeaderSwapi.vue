<template>
  <header>
    <h1>STAR WARS <span>films project</span></h1>
  </header>
</template>

<style scoped>
header {
  background: linear-gradient(
    to bottom,
    rgba(30, 30, 30, 0.5) 40%,
    rgba(30, 30, 30, 0.7) 90%
  );
  z-index: 2;
  padding: 2%;
}

header h1 {
  font-family: "StarWars";
  text-align: center;
  font-size: 4vw;
  width: 30%;
  margin: auto;
  color: #c9b823;
  line-height: 1;
}

header h1 > span {
  font-family: "StarWars2";
  font-size: 2vw;
  color: #bbb798;
}

@media screen and (max-width: 800px) {
  header {
    padding: 3%;
  }

  header h1 {
    font-size: 6vw;
    width: 40%;
  }

  header h1 > span {
    font-size: 3vw;
  }
}

@media screen and (max-width: 420px) {
  header {
    padding: 5%;
  }

  header h1 {
    font-size: 8vw;
    width: 60%;
  }

  header h1 > span {
    font-size: 4vw;
  }
}
</style>
