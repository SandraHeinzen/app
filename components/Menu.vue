<template lang='pug'>
div(class='container-menu')
  div(class='menu')
    ul(class='menu__list')
      li(
        v-for='(card, i) in menuData'
        :key='card + i'
        class='menu__item'
      )
        Card(
          :cardData='{ headline: card.headline, id: card.id, path: card.id }'
          :style='{ backgroundColor: card.color }'
          class='menu__card'
        )
</template>


<script>
import Card from '~/components/Card.vue'


export default {
  components: {
    Card
  },
  props: {
    menuData: {
      type: Array,
      required: true
    }
  },
  data () {
    return {}
  },
  computed: {},
  methods: {}
}
</script>


<style lang='sass' scoped>
.container-menu
  @extend %container-main

.menu
  @extend %container-content

  &__list
    display: grid
    grid-template-rows: repeat(2, $unit*20)
    grid-template-columns: repeat(3, 1fr)
    grid-gap: $unit*6 $unit*4

  &__item

  &__card
</style>
