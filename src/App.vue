<template>
<div>
    <ul>
      <li v-for="(item, index) in items" :key="index" :class="itemClass(index)" @click="toggleBold(index)">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  data() {
    return {
      items: ['item1', 'item2', 'item3'],
        boldIndex: null,
    };
  },
  methods: {
    itemClass(item) {
      if (this.boldIndex === item) {
        return 'bold';
      } else {
        return 'normal';
      }
    },
    toggleBold(index) {
        console.log("is clicked", index)
      if (this.boldIndex === index) {
        this.boldIndex = null;
      } else {
        this.boldIndex = index;
      }
    },
  },
    beforeMount() {
        console.log("mounted")
        this.boldIndex = 0;
    },
}
</script>

<style scoped>
.bold {
  font-weight: bold;
}
.normal {
  font-weight: normal;
}

.login {
  display: flex;
  flex-direction: column;
  row-gap: 5px;
}


.divide {
  display: flex;
  flex-direction: row;
  column-gap: 20px;
}

</style>
