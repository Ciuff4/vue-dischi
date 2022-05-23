<template>
    <select class="form-select" title="Scegli un'opzione" v-model="selectedGenre"
    @change="$emit('changeGenre' , selectedGenre)">
        <option value="Jazz">Jazz</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Metal">Metal</option>
    </select>
</template>

<script>
export default {
name:'SelectComponent',
data(){
    return{
        selectedGenre:""
    }
},
props:{
        
    }
// methods:{
//     changeGenre(){
//         this.$emit(changeGenre , genre );
//         this.selectedGenre=''
//     }
// }

}
</script>

<style lang="scss" scoped>
select{
    margin-right: 20px;
    width: 200px;
}
</style>