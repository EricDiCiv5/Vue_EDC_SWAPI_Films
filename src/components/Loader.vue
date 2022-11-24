<template>
  <span class="loader"></span>
</template>

<style scoped>
.loader {
  width: 20vh;
  height: 20vh;
  border: 3px solid rgb(172, 184, 219);
  border-radius: 50%;
  display: block;
  position: relative;
  box-sizing: border-box;
  animation: rotation 1s linear infinite;
  margin: 2vh auto;
}
.loader::after {
  content: '""';
  box-sizing: border-box;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 19vh;
  height: 19vh;
  border-radius: 50%;
  border: 8px groove;
  border-color: #c9b823 transparent;
}

@keyframes rotation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
