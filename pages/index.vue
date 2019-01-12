<template>
  <div>
    <h1 v-text="title"/>
    <input v-model="input"/>
    <pre v-text="reversed"/>
  </div>
</template>

<script lang="ts">
  import { State } from 'vuex-class'
  import { Component, Vue } from 'nuxt-property-decorator'
  import { reverseString } from '~/core/utils'

  @Component
  export default class extends Vue {

    @State public title!: string;

    public input = 'TypeScript';

    head() {
      return {
        title: this.title
      }
    }

    get reversed(): string {
      return reverseString(this.input)
    }
  }
</script>
