<template>
    <select name="generi" id=""
    @change="$emit(changeGenre , genre)">
        <option value="all">seleziona un genere</option>
        <option value="jazz">Jazz</option>
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="metal">Metal</option>
    </select>
</template>

<script>
export default {
name:'SelectComponent'
}
</script>

<style lang="scss" scoped>
select{
    margin-right: 20px;
    width: 70px;
}
</style>