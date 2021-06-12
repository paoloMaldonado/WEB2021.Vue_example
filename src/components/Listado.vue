<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Nombre</th>
          <th class="text-left">Apellido</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in desserts" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.calories }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>


<script>
import axios from "axios";

export default {
  data() {
    return {
      clientes: [],
      desserts: [],
    };
  },
  created() {
    this.loadCustomers();
  },
  methods: {
    loadCustomers() {
      let url = "http://localhost:11188/swagger/index.html";

      axios
        .get(url, {})
        .then((response) => {
          console.log(response);
          this.clientes = response.data;
        })
        .catch((error) => {
          console.log(error);
        });

      console.log("Cagando clientes.....");
    },
  },
};
</script>