<template>
    <div class="col-2 cg-card">
        <div class="cover">
            <img :src="cardItem.poster" :alt="cardItem.title">
        </div>
        <h5>{{cardItem.title}}</h5>
        <p>{{cardItem.author}}</p>
        <p>{{cardItem.year}}</p>
    </div>
</template>

<script>
export default {
name:'CardComponent',
props:{
    cardItem:Object
}
}
</script>

<style lang="scss" scoped>
.cg-card{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #2E3A46;
    margin: 10px;
    height: 300px;
    .cover{
        height: 90px;
        width: 90px;
    }
    h5{
        color: white;
        padding:  10px 0;
        text-align: center;
    }
    p{
        color: #676769;
    }
}
</style>