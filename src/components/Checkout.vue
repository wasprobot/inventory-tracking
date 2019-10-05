<template>
  <div>
    <md-card-content>
      <div class="md-layout md-gutter">
        <div class="md-layout-item md-small-size-100">
          <md-field>
            <label for="item">What are you looking for?</label>
            <md-input name="item" id="item" v-model="form.item" />
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
    }
  })
};
</script>