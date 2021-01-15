<template>
  <ul class="c-rainbow">
    <li class="c-rainbow__layer c-rainbow__layer--orange">{{ text }}</li>
    <li class="c-rainbow__layer c-rainbow__layer--red">{{ text }}</li>
    <!--<li class="c-rainbow__layer c-rainbow__layer&#45;&#45;violet">Cyber flaners</li>-->
    <li class="c-rainbow__layer c-rainbow__layer--blue">{{ text }}</li>
    <li class="c-rainbow__layer c-rainbow__layer--green">{{ text }}</li>
    <li class="c-rainbow__layer c-rainbow__layer--yellow">{{ text }}</li>
  </ul>
</template>

<script>
export default {
  name: 'RainbowTitle',
  props: ['text']
}
</script>

<style lang="scss">

$root: '.c-rainbow';

:root {
  --color-background: #31037D;

  --axis-x: 1px;
  --axis-y: 0.6rem;
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
      animation-play-state: running;
    }
  }

  &__layer {
    --text-color: var(--color-foreground);
    counter-increment: rainbow;
    font-size: 2rem;
    color: var(--text-color);

    text-shadow: -1px -1px 0 var(--color-black),
    1px -1px 0 var(--color-black),
    -1px 1px 0 var(--color-black),
    1px 1px 0 var(--color-black),
    4px 4px 0 rgba(0, 0, 0, .2);

    animation: rainbow 1.5s ease-in-out infinite;
    animation-play-state: paused;

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
    transform: translatey(0.3rem);
  }
  50% {
    transform: translatey(calc(0.3rem * -1));
  }
}

</style>
