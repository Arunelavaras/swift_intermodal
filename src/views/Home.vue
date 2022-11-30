
<template>
  <div class="home">
      <table class="table table-striped table-bordered">
        <thead class="thead-light">
          <tr>
            <th scope="col">Load ID</th>
            <th scope="col">Status</th>
            <th scope="col">Customer Name</th>
            <th scope="col">Orgin</th>
            <th scope="col">Destination</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in items" :key="item.load_id">
            <td>{{ item.load_id }}</td>
            <td>{{ item.status }}</td>
            <td>{{ item.cust_name }}</td>
            <td>{{ item.orgin }}</td>
            <td>{{ item.dest }}</td>
          </tr>
        </tbody>
      </table>
    </div>
</template>
  
<script  lang="ts">
import { defineComponent } from 'vue';
export default defineComponent ({
  name: 'HomeNew',
  components: {
    
},
  data() {
    return {
      items: [
        { load_id: 'L001', status: 'A', cust_name: 'Messi', orgin: 'Phoenix', dest: 'Denver' },
        { load_id: 'L002', status: 'D', cust_name: 'Ronaldo', orgin: 'California', dest: 'Illinois' },
        { load_id: 'L003', status: 'D', cust_name: 'Neymar', orgin: 'Miami', dest: 'Atlanta' },
        { load_id: 'L004', status: 'A', cust_name: 'Robert', orgin: 'Texas', dest: 'Kansas' }
      ]

    }
  }
})
</script>

<style scoped>
.home {
  margin-top: 150px;
  /* border: 1px solid grey; */
  margin-left: 5px;
  margin-right: 5px;
 

}

th {
  background-color: #cecece !important;
}
</style>
  