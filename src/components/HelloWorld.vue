<script>
export default {
  name: "HelloWorld",

  data: () => ({
    desserts: [
      {
        name: 'Frozen Yogurt',
        calories: 159,
      },
      {
        name: 'Ice cream sandwich',
        calories: 237,
      },
      {
        name: 'Eclair',
        calories: 262,
      },
      {
        name: 'Cupcake',
        calories: 305,
      },
      {
        name: 'Gingerbread',
        calories: 356,
      },
      {
        name: 'Jelly bean',
        calories: 375,
      },
      {
        name: 'Lollipop',
        calories: 392,
      },
      {
        name: 'Honeycomb',
        calories: 408,
      },
      {
        name: 'Donut',
        calories: 452,
      },
      {
        name: 'KitKat',
        calories: 518,
      },
    ],
  })
}
</script>

<template>
  <v-container>
    <div>
      <v-text-field
        label="primabvara">
      </v-text-field>

      <v-simple-table>
        <template v-slot:default>
          <thead>
          <tr>
            <th class="text-left">Name</th>
            <th class="text-left">Calories</th>
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

     <div class="d-fex">
       <div >
         <v-btn color="default">Primary</v-btn>
       </div>
       <div >
         <v-btn color="secondary">Primary</v-btn>
       </div>
       <div >
         <v-btn color="info">Primary</v-btn>
       </div>
       <div class="ml-2">
         <v-btn color="success">Primary</v-btn>
       </div>
       <div class="ml-2">
         <v-btn  color="primary">Primary</v-btn>
       </div>
       <div class="ml-2">
         <v-btn  color="warning">Primary</v-btn>
       </div>
       <div class="ml-2">
         <v-btn  color="error">Primary</v-btn>
       </div>
     </div>

      <v-card>
        <div style="padding: 50px 0"  class="card">
          aaaaa goriu
        </div>
      </v-card>

    </div>
  </v-container>
</template>

<style scoped>
  .card {
    background: var(--v-secondary-base);
  }
</style>
