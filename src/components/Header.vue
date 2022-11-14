<template>
    <header>
        <h1>{{title}}</h1>
        <Button text="Submit" color="green" />
    </header>
</template>

<script>
import Button from './button/Button.vue'
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header',
  props: {
    title: String
  },
  components: {
    Button
  }

}

</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>
