<script lang='ts' setup>
import ListItem from './ListItem.vue'
import { ref } from 'vue'
import type { Ref } from 'vue'

// Definimos el tipo para un elemento de la lista
type Item = {
  title: string,
  checked?: boolean
}

// Creamos un array de elementos de la lista con su estado
const listItems: Ref<Item[]> = ref( [
  { title: 'Make a todo list app', checked: true },
  { title: 'Predict the weather', checked: false },
  { title: 'Play some tunes', checked: false },
  { title: 'Let\'s get cooking', checked: false },
  { title: 'Pump some iron', checked: false },
  { title: 'Track my expenses', checked: false },
  { title: 'Organize a game night', checked: false },
  { title: 'Learn a new language', checked: false },
  { title: 'Publish my work' } // Este elemento no tiene la propiedad "checked"
])

</script>

<template>
  <ul>
    <!-- Iteramos sobre los elementos de la lista -->
    <li v-for='(item, key) in listItems' :key='key'>
      <!-- Usamos el componente ListItem para cada elemento -->
      <ListItem :is-checked='item.checked'>{{ item.title }}</ListItem>
    </li>
  </ul>
</template>

<style scoped>
ul {
  list-style: none;
}
li {
  margin: 0.4rem 0;
}
</style>
