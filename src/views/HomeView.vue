<template>
  <div class="home">
    <div
    v-for="(categoryItems, categoryName) in categorizedItems"
    :key="categoryName"
    class="column">
      <h2>{{ categoryName }}</h2>
      <ItemComponent v-for="item in categoryItems" :key="item.id" :originalItem="item"/>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ItemComponent from '@/components/ItemComponent.vue';

interface Item {
  id: string;
  category: string;
  name: string;
  description: string;
  checked: boolean;
  createdat: string;
  updatedat: string;
}

export default defineComponent({
  name: 'HomeView',
  components: {
    ItemComponent,
  },
  data() {
    return {
      items: [
        {
          id: 'string',
          category: 'outro',
          name: 'string',
          description: 'string',
          checked: false,
          createdat: 'Date',
          updatedat: 'Date',
        },
        {
          id: 'string',
          category: 'outro',
          name: 'string',
          description: 'string',
          checked: false,
          createdat: 'Date',
          updatedat: 'Date',
        },
      ],
    };
  },
  computed: {
    categorizedItems() {
      const result: Record<string, Item[]> = {};
      this.items.forEach((item) => {
        if (!result[item.category]) {
          result[item.category] = [];
        }
        result[item.category].push(item);
      });
      return result;
    },
  },
});
</script>

<style scoped>
.column {
  display: inline-block;
  vertical-align: top;
  margin: 0 20px;
}
.item {
  margin-bottom: 10px;
}
</style>
