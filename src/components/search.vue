<template>
  <div class="page-search">
    <mt-search autofocus v-model="value" :result="filterResult"></mt-search>
  </div>
</template>

<script>
export default {
  data () {
    return {
      value: '',
      defaultResult: [
        'Apple',
        'Banana',
        'Orange',
        'Durian',
        'Lemon',
        'Peach',
        'Cherry',
        'Berry',
        'Core',
        'Fig',
        'Haw',
        'Melon',
        'Plum',
        'Pear',
        'Peanut',
        'Other'
      ]
    }
  },
  computed: {
    filterResult () {
      return this.defaultResult.filter(value => new RegExp(this.value, 'i').test(value))
    }
  }
}
</script>

<style lang="css" scoped>
  .page-search {
    height: 100%;
  }
</style>
