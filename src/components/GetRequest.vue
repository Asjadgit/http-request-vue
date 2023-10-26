<template>
    <button @click="getdata()">Get Data</button>

    <div class="table">
    <h2>Fetch Data By Using Api</h2>
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Title</th>
          <th>Body</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="i in data" :key="i.id">
          <td>{{ i.id }}</td>
          <td>{{ i.title }}</td>
          <td>{{ i.body }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios';
    export default{
        name : 'GetRequest',
        data(){
            return{
                data : [],
            }
        },
        methods:{
            getdata(){
                axios.get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => {
                    this.data = response.data;
                })
                
            }
        }
    }
    
</script>