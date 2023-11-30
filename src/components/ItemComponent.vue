<!-- eslint-disable vuejs-accessibility/label-has-for -->
<template>
  <div class="item">
    <div>
      <label for="category">Category:</label>
      <span id="category">{{ item.category }}</span>
    </div>
    <div>
      <label for="name">Name:</label>
      <span id="name">{{ item.name }}</span>
    </div>
    <div>
      <label for="description">Description:</label>
      <span id="description">{{ item.description }}</span>
    </div>
    <div>
      <label for="created">Created:</label>
      <span id="created">{{ item.created }}</span>
    </div>
    <div>
      <label for="updated">Updated:</label>
      <span id="updated">{{ item.updated }}</span>
    </div>
    <div>
      <label for="checked">Checked:</label>
      <input type="checkbox" id="checked" v-model="item.checked" />
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    originalItem: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      item: { ...this.originalItem },
    };
  },
};
</script>

<style scoped>
.item {
  border: 1px solid #ddd;
  padding: 10px;
  margin: 10px;
}
</style>
