<template>
    
    <div class="add-todo">
            
            <input class="add-input" type="text" v-model="item.name"  />
           
            <button @click="addItem()">Add Item</button>
            
        </div>
    
</template>

<script>
import axios from 'axios'

export default {
    data() {
        return{
            item: {
                name:""
            }
        }
    },
    methods: {
        addItem () {
            if(this.item.name == ''){
                return ;
            }
            axios.post('api/item/store', {
                item: this.item
            })
            .then(response =>{
                if(response.status = 201 ){

                    this.item.name = '';
                }
            })
            .catch (error => {
                console.log(error);
            })

        }
    }
}
</script>

<style>
    .add-todo{
        display:flex;
        justify-content: center;
        padding:1em;
      
    }
    .add-input{
        width:100%;
        border:0;
        outline:none;
        padding :1em;
        background-color: beige;
        margin-right:6px;
        

    }
</style>