<template>

    <div>
        <h1> {{book.day}}</h1>
        <h2> {{book.category}}</h2>
        <section id="nameof"><h4> Type of workout : {{book.typeofworkout}}</h4></section>
        <h4> Difficulty : {{book.difficulty}}</h4>
        <h4> Sets : {{book.sets}}</h4>
        <h4> Reps : {{book.reps}}</h4>
        <h4> Rest Time : {{book.resttime}}</h4>
        
    </div>

</template>

<script>




export default{
    name: 'BookItem',
    props:{
        book: Array
    }
}


</script>

<style scoped>

h2{
    text-align: center;
}
h4{
    margin: 2px;
}
h1{
    text-align: center;
}
#nameof{
    background-color: #b1ff9e;
    color: black;
    padding: 1em;

}
div{
    background-color: #ffb89e;
    color: black;
    padding: 1em;
}

.red{
background-color: orangered !important;

}
.green{
    color: white;
}


</style>
