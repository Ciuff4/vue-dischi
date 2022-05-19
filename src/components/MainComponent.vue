<template>
    <div>
        <div class="container">
            <div class="row">
                <CardComponent
                v-for="(card , index) in cardList" :key="`cards-${index}`"
                :cardItem='card' />
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue'

export default {
name:'MainComponent',
components:{
    CardComponent,
},
data(){
    return{
        apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
        cardList:[]
    }
},
mounted(){
        this.getApi();
},
methods:{
    getApi(){
        axios.get(this.apiUrl)
        .then(response=>{
            console.log(response.data);
            this.cardList=response.data.response
        })
        .catch(e=>{
            console.log(e);
        })
    }
}
}
</script>

<style lang="scss" scoped >
div{
    justify-content: space-between;
    background-color: #1E2D3B;
}
</style>