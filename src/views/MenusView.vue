<template lang="pug">
  doc-view(v-bind:doc="doc" id="menus-view")
    component-example(header="On Click" file="menus/1" v-bind:data="$data")
    component-example(header="Menus" file="menus/3" v-bind:data="$data")
    component-example(header="Custom Transitions" file="menus/4" v-bind:data="$data")
      section-text(slot="details") Vuetify comes with 3 standard transitions, <strong>scale</strong>, <strong>slide-x</strong> and <strong>slide-y</strong>. You can also create your own and pass it as the transition argument. For an example of how the stock transitions are constructed, visit <a href="https://github.com/vuetifyjs/vuetify/blob/master/src/util/helpers.js#L13" target="_blank">here</a>.
</template>

<script>
  import ItemProps from '../constants/itemable-props'

  export default {
    data () {
      return {
        doc: {
          title: 'Menu',
          desc: `The <code>v-menu</code> component utilizes the v-menu directive to link itself to another element. Once binded, clicking the element, or by hovering (if using the <code>hover</code> parameter), the menu will reposition absolutely positioned on top of the selected activator.`,
          props: {
            'v-menu': {
              params: [
                [
                  'top',
                  'Boolean',
                  'False',
                  'Set top coordinate for menu'
                ],
                [
                  'right',
                  'Boolean',
                  'False',
                  'Set right coordinate for menu'
                ],
                [
                  'bottom',
                  'Boolean',
                  'False',
                  'Set bottom coordinate for menu'
                ],
                [
                  'left',
                  'Boolean',
                  'False',
                  'Set left coordinate for menu'
                ],
                [
                  'origin',
                  'String',
                  'top left',
                  'Set the transform-origin of the transition'
                ],
                [
                  'transition',
                  'String',
                  'v-scale-transition',
                  'Set the transition component'
                ]
              ]
            }
          },
          slots: {
            'v-menu': {
              params: [
                [
                  'activator',
                  'The element that will activate the menu'
                ]
              ],
              default: true
            }
          }
        },
        items: [
          {
            title: 'Click Me'
          },
          {
            title: 'Click Me'
          },
          {
            title: 'Click Me'
          },
          {
            title: 'Click Me 2'
          }
        ]
      }
    },

    mounted () {
      this.$emit('view', this.meta())
    },

    preFetch () {
      return this.methods.meta()
    },

    methods: {
      meta () {
        return {
          title: 'Menu Component | Vuetify.js',
          h1: 'Menus',
          description: 'Menu component for Vuetify Framework',
          keywords: 'vuetify, menus, components'
        }
      }
    }
  }
</script>

<style lang="stylus">
  #menus-view
    .btn
      margin: 1rem
      
    .component-example__container
      .card
        flex: 1
        margin: 1rem
        
        &__text
          height: 200px
</style>