<template>
  <footer>
    <p>&copy; Eric Díaz. 2022</p>
    <article>
      <a
        href="https://github.com/EricDiCiv5"
        target="_blank"
        rel="noopener noreferrer"
      >
        <i class="fa-brands fa-github"></i>
      </a>
      <a
        href="https://www.linkedin.com/in/ericd%C3%ADazc%C3%ADvico/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <i class="fa-brands fa-linkedin"></i>
      </a>
    </article>
  </footer>
</template>

<style scoped>
footer {
  background: linear-gradient(
    to bottom,
    rgba(30, 30, 30, 0.5) 40%,
    rgba(30, 30, 30, 0.7) 90%
  );
  z-index: 2;
  padding: 1.8%;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  font-family: "Space Grotesk";
  font-size: 1.1vw;
  color: #dcdcdc;
}

footer p {
  flex: 11;
}

footer article {
  flex: 1;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}

footer article > a > i {
  color: #dcdcdc;
  font-size: 1.7vw;
}

@media screen and (max-width: 800px) {
  footer {
    padding: 3%;
    font-size: 1.75vw;
  }

  footer article {
    flex: 1;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
  }

  footer article > a > i {
    color: #dcdcdc;
    font-size: 2.5vw;
  }
}

@media screen and (max-width: 420px) {
  footer {
    padding: 3%;
    font-size: 1.75vw;
  }

  footer article {
    flex: 1;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
  }

  footer article > a > i {
    color: #dcdcdc;
    font-size: 2.5vw;
  }
}
</style>
