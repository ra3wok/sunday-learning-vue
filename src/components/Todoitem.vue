<template>
  <li>
    <span v-bind:class="{done: NameElement.completed}">
      <input type="checkbox" v-on:change="NameElement.completed = !NameElement.completed" />
      <strong>{{NameElement.id}}</strong>
      {{NameElement.title}}
    </span>
    <button class="rm" v-on:click="$emit('remove-Element', NameElement.id)">&times;</button>
  </li>
</template>

<script>
export default {
  name: "Todoitem",
  props: ['NameElement'],
}
</script>

<style scoped>
li {border: 1px solid gray;
display: flex;
justify-content: space-between;
padding: .5rem 2rem;
marging-bottom: 1rem;
}

.rm {background: #2c3e50;
color: #fff;
border-radius: 50%;
font-weight: bold;
}

input{margin-right: 1rem;
}

.done {text-decoration: line-through;}
</style>