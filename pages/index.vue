<template>
  <full-page>
    <div class="section header" :class="{'loaded': isLoad}">
      <div class="header-menu">
        <span>Меню</span>
      </div>
      <WhiteNoise :time="2"/>
      <div class="header-flaners">
        <div class="header-flaners__ed">
          <img src="/img/photo-flaners/ed.png" alt="">
        </div>
        <ul class="c-rainbow">
          <li class="c-rainbow__layer c-rainbow__layer--orange">Cyber flaners</li>
          <li class="c-rainbow__layer c-rainbow__layer--red">Cyber flaners</li>
          <!--<li class="c-rainbow__layer c-rainbow__layer&#45;&#45;violet">Cyber flaners</li>-->
          <li class="c-rainbow__layer c-rainbow__layer--blue">Cyber flaners</li>
          <li class="c-rainbow__layer c-rainbow__layer--green">Cyber flaners</li>
          <li class="c-rainbow__layer c-rainbow__layer--yellow">Cyber flaners</li>
        </ul>
      </div>
    </div>
    <div class="section">
      <div class="container-fluid">
        <div class="row">
          <div class="col-3">
            <h2>Наши проекты</h2>
          </div>
          <div class="col-9">
            <div class="projects">
              <div class="project-item">
                <img src="/img/my-game.jpg" alt="">
              </div>
              <div class="project-item">

              </div>
              <div class="project-item">

              </div>
              <div class="project-item">

              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </full-page>
</template>

<script>
import WhiteNoise from '../components/animations/WhiteNoise.vue'

export default {
  components: {
    WhiteNoise
  },
  data() {
    return {
      isLoad: false,
    }
  },
  mounted() {
    this.isLoad = true
  }
}
</script>

<style lang="scss">
@import "../assets/scss/bootstrap-grid.scss";
@import "../assets/scss/index.scss";

body {
  background-color: #000;
  color: #FFF;
}

$root: '.c-rainbow';

:root {
  --color-background: #31037D;

  --axis-x: 1px;
  --axis-y: 1rem;
  --delay: 10;

  --color-black: #000;
  --color-white: #fff;
  --color-orange: #D49C3D;
  --color-red: #D14B3D;
  --color-violet: #CF52EB;
  --color-blue: #44A3F7;
  --color-green: #5ACB3C;
  --color-yellow: #DEBF40;

  --color-foreground: var(--color-white);
  --font-name: Righteous;
}

#{$root} {
  counter-reset: rainbow;
  position: relative;
  display: block;

  list-style: none;

  padding: 0;
  margin: 0;

  &:hover {
    #{$root}__layer {
      animation-play-state: paused;
    }
  }

  &__layer {
    --text-color: var(--color-foreground);
    counter-increment: rainbow;
    font-size: 6rem;
    color: var(--text-color);

    text-shadow: -1px -1px 0 var(--color-black),
    1px -1px 0 var(--color-black),
    -1px 1px 0 var(--color-black),
    1px 1px 0 var(--color-black),
    4px 4px 0 rgba(0, 0, 0, .2);

    animation: rainbow 1.5s ease-in-out infinite;

    @for $i from 1 through 7 {
      &:nth-child(#{$i}) {
        animation-delay: calc(#{$i} / var(--delay) * 1s);
        left: calc(var(--axis-x) * #{$i});
        z-index: -#{$i * 10};
      }
    }

    &:not(:first-child) {
      z-index: 5;
      position: absolute;
      width: 100%;
      top: 0;
      left: 0;
    }

    &--white {
      --text-color: var(--color-white)
    }

    &--orange {
      --text-color: var(--color-orange)
    }

    &--red {
      --text-color: var(--color-red)
    }

    &--violet {
      --text-color: var(--color-violet)
    }

    &--blue {
      --text-color: var(--color-blue)
    }

    &--green {
      --text-color: var(--color-green)
    }

    &--yellow {
      --text-color: var(--color-yellow)
    }
  }
}

@keyframes rainbow {
  0%, 100% {
    transform: translatey(1rem);
  }
  50% {
    transform: translatey(calc(1rem * -1));
  }
}

@keyframes flyEd {
  0% {
    bottom: 30%;
    left: -15%;
    transform: rotate(90deg);
  }
  75% {
    bottom: 30%;
    left: 30%;
    transform: rotate(90deg);
  }
  85% {
    bottom: 30%;
    left: 30%;
    transform: rotate(0);
  }
  100% {
    bottom: 0;
    left: 30%;
    transform: rotate(0);
  }
}

</style>

