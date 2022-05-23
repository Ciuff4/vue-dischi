<template>
    <div>
        <SelectComponent
        @changeGenre="changeGenre"
        />
        <div class="container">
            <div class="row">
                <CardComponent
                v-for="( card , index) in newArray" :key="`cards-${index}`"
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
        cardList:[],
        genere:'',
        newArray:[]
    }
},
mounted(){
        this.getApi();
        this.changeGenre(this.selectedGenre);
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
    },
    changeGenre(selectedGenre){
        this.genere=selectedGenre;
    },

    

},
computed:{
    cambioArray(){
        if (this.genere===undefined) {
            return this.cardList
        }else{
            for (let cardItem of this.cardList) {
            if (cardItem.genre===this.genere) {
                this.newArray.push(cardItem)
                }
            }
            return this.newArray
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