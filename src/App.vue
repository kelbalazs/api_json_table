<template>
  <div id="app">
<table>
      <thead>
        <tr>
          <th>id</th>
          <th>meta</th>
          <th>title</th>
          <th>is private</th> 
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.meta }}</td>
          <td>{{ item.title }}</td>
          <td>{{ item.is_private }}</td>
        </tr>
      </tbody>

    </table>
  
  </div>

</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      items:''
    }
  },


  created() {
    axios.get(`https://zbeta2.mykuwaitnet.net/backend/en/api/v2/pages/`)
    .then(response => {
     
      this.items = response.data.items
    })
    
  }
}



</script>

<style>


 table, th, td {
  
  border: 1px solid black;
 }
th {
  background-color:mediumseagreen;
  color: white;
}
</style>
