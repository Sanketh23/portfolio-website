<template>
  <card :card-width="cardWidth">
    <h3 class="card-title">
      {{ title }}
      <div v-if="rocketcrab" class="rocketcrab-superscript">
        <img src="https://rocketcrab.com/rocketcrab-logo-text.svg" />
      </div>
    </h3>

    <div class="card-text">
      <slot></slot>
    </div>

    <div v-if="buttonHref || buttonText">
      <a :href="buttonHref" target="_blank" rel="noopener">
        <button type="button" class="btn btn-outline-light">
          {{ buttonText || 'Learn more' }}
        </button>
      </a>
    </div>
  </card>
</template>

<script>
import Card from './Card.vue'
export default {
  name: 'ProjectCard',
  components: { Card },
  props: {
    title: { type: String, default: '' },
    buttonHref: { type: String, default: '' },
    buttonText: { type: String, default: '' },
    cardWidth: { type: String, default: '6' },
    rocketcrab: { type: Boolean, default: false }
  }
}
</script>

<style>
.card-title {
  font-family: 'Jost', sans-serif;
  font-size: 2rem;
  font-weight: 500;
  font-style: italic;
}
.card-subtitle {
  font-style: italic;
}
.rocketcrab-superscript {
  display: inline-block;
  overflow: hidden;
  width: 1.6em;
  margin-left: -0.4em;
  margin-bottom: 0.4em;
  margin-top: -1em;
}
.rocketcrab-superscript img {
  margin: -1.4em -0.2em -1.6em -0.2em;
}
</style>
