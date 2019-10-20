<template>
  <div>
    <md-card-content>
      <div class="md-layout md-gutter">
        <div class="md-layout-item md-small-size-100">
          <md-field>
            <label for="item">What are you checking out?</label>
            <md-select name="item" id="item">
              <md-option v-for="item in items" :value="item.name" :key="item.index">{{ item.name }}</md-option>
            </md-select>
          </md-field>
        </div>
      </div>
    </md-card-content>
  </div>
</template>

<script scoped>
export default {
  name: "Checkout",
  data: () => ({
    form: {
      item: null
    },
    items: [{ name: "item-1" }, { name: "item-2" }]
  }),
  mounted() {}
};
</script>