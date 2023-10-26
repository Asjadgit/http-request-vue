<template>
    <div>
        <form @submit.prevent="addPost" class="my-form">
            <div class="id">
                <label for="userid">Post User id</label><br>
                <input type="text" id="userid" v-model="formData.id">
            </div>
            <div class="title">
                <label for="title">Post title</label>
                <input type="text" id="title" v-model="formData.title">
            </div>
            <div class="body">
                <label for="body">Post body</label>
                <input type="text" id="body" v-model="formData.body">
            </div>

            <button class="my-btn">Add Post</button>
        </form>

        

    </div>
</template>


<script>
import axios from 'axios';
export default{
    name : 'PostRequest',
    data(){
        return{
            formData:{
                id : '',
                title : '',
                body : ''
            }
        }
    },
    methods:{
        addPost(){
            axios.post('https://jsonplaceholder.typicode.com/posts',this.formData)
            .then((response) => {
                console.log('Data inserted ', response.data);
                this.formData = {id : '', title: '', body: ''};
            })
        }
    }
}
</script>

<style>
.my-form {
  margin: 20px;
  width: 300px;
  height: 300px;
  background: #834aad;
  color: #fff;
  border-radius: 4px;
  position: absolute;
  top: 10%;
  left: calc(50% -  150px);
}
input{
    padding: 5px 10px;
    width: 200px;
    border: none;
    border-radius: 3px;
    outline: none;
    background-color: #fff;
    margin-bottom: 20px;
    margin-left: 20px;
}
.id,.title,.body{
    margin-top: 10px;
}

.my-btn {
  background-color: #007BFF;
  color: #fff;
  border: none;
  border-radius: 3px;
  padding: 8px 16px;
  cursor: pointer;
  transition: 0.4s;
}
.my-btn:hover{
    letter-spacing: 2px;
    background-color: #007Bee;
}

</style>