<template>
    <div>
        <SelectComponent
            @changeGenre='changeSelect' />
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
import SelectComponent from "./SelectComponent.vue";
import CardComponent from './CardComponent.vue'

export default {
name:'MainComponent',
components:{
    SelectComponent,
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
},

computed:{
    changeArrayMusic(genre){
        let filteredArray=[];
        if(option.value=== all){
            filteredArray=this.cardList;
        }else{
            filteredArray=this.cardList.filter(card=>{
                return card.genre.toUpperCase()===option.value.toUpperCase()
            })
        }
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