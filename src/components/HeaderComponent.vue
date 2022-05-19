<template>
    <div>
        <div class="col-sx">
            <img src="../assets/img/logo-small.svg" alt="">
        </div>
        <div class="col-dx">
            <select name="generi" id="">
                <option value="jazz">Jazz</option>
                <option value="rock">Rock</option>
                <option value="punk">Punk</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
name:'HeaderComponent'
}
</script>

<style lang="scss" scoped>
div{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #29323B;
    height: 50px;
    img{
        margin-left: 20px;
        height: 90%;
        filter:contrast(0) sepia(100%) hue-rotate(80deg) brightness(1.4) saturate(5);
    }
    select{
        margin-right: 20px;
        width: 70px;
    }
}
</style>