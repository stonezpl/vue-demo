<template>
  <ul>
    <li v-for="item in items" :key="item.id">
        {{item.name}}{{item.title}}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          id: 1,
          name: "name1",
          title: "title1"
        },
        {
          id: 2,
          name: "name2",
          title: "title2"
        }
      ]
    };
  }
};
</script>