<template>
  <div class="list-item">
    <span class="budget-comment">{{ item.comment }}</span>
    <span class="budget-value">{{ item.value }}</span>
    <ElButton type="danger" size="mini" @click="onDeleteItem(item.id)">Delete</ElButton>
  </div>
</template>

<script>
export default {
  name: "BudgetListItem",
  props: {
    item: {
      type: Object,
      default: () => ({})
    }
  },
  methods: {
    onDeleteItem(id) {
      this.$emit("deleteItem", id);
    }
  }

}
</script>

<style scoped>
  .list-item {
    display: flex;
    align-items: center;
    padding: 10px 15px;
  }

  .budget-value {
    font-weight: bold;
    margin-left: auto;
    margin-right: 20px;
  }
</style>