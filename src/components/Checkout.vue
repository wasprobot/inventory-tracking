<template>
  <div>
    <md-card-content>
      <div class="md-layout md-gutter">
        <div class="md-layout-item md-small-size-100">
          <md-field>
            <label for="item">What are you looking for?</label>
            <md-input name="item" id="item" v-model="form.item"/>
          </md-field>
        </div>
      </div>
    </md-card-content>
  </div>
</template>

<script scoped>
const { Client } = require("pg");

export default {
  name: "Checkout",
  data: () => ({
    form: {
      item: null
    }
  }),
  mounted: function() {
    const client = new Client({
      connectionString:
        "postgres://eqvwgfsypvkgag:df2583a32354bdcec4fdb64cf01319898b7af20995eb8815a83addd51df1b1d3@ec2-54-235-163-246.compute-1.amazonaws.com:5432/dalp6cn0knb1ou",
      ssl: true
    });

    client.connect();

    client.query(
      "SELECT table_schema,table_name FROM information_schema.tables;",
      (err, res) => {
        if (err) throw err;
        for (let row of res.rows) {
          console.log(JSON.stringify(row));
        }
        client.end();
      }
    );
  }
};
</script>