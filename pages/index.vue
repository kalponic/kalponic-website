<template>
  <div class="page">
    <div class="wrapper">
      <div>
        <h1 class="title">
          Kalponic Games
        </h1>
        <h2 class="subtitle">
          PRESS ENTER
        </h2>
      </div>
      <!-- <div class="transition-box">
        <div class="row"></div>
        <div class="row"></div>
        <div class="row"></div>
      </div> -->
    </div>
    <div class="test">Hello</div>
  </div>
</template>

<script>
export default {
  mounted() {
    document
      .querySelector('h2.subtitle')
      .addEventListener('click', this.openSite)
    document.addEventListener('keyup', (e) => {
      if (e.code === 'Enter') {
        this.openSite()
      }
    })
  },
  methods: {
    openSite() {
      document.querySelector('.wrapper').classList.add('animate')
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.wrapper {
  z-index: 5;
  position: fixed;
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  background-color: black;
  align-items: center;
  text-align: center;

  width: 100vw;
  height: 100vh;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  word-spacing: 5px;
  padding-bottom: 15px;
  animation-name: textBlink;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
  animation-duration: 1s;
}

/* .transition-box {
  width: 100%;
  position: fixed;
  bottom: 100%;
  display: flex;
  flex-direction: column;
}

.transition-box .row {
  height: 1rem;
  width: 100%;
  animation-name: toggleColor;
  animation-iteration-count: infinite;
  animation-duration: 0.1s;
}

.transition-box .row:nth-child(even) {
  animation-direction: reverse;
} */

.animate {
  animation-name: transitionBox;
  animation-duration: 1s;
  animation-fill-mode: forwards;
  animation-timing-function: ease-in;
}

/* @keyframes toggleColor {
  from {
    background-color: white;
  }

  to {
    background-color: black;
  }
} */

@keyframes transitionBox {
  from {
    bottom: 0;
  }

  to {
    bottom: 100%;
  }
}

@keyframes textBlink {
  from {
    color: white;
  }

  to {
    color: black;
  }
}
</style>
