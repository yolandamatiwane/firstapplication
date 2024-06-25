<template>
    <div :style="{
        backgroundImage: `url(${cover})`,
        backgroundSize:'cover',
        filter: 'blur(1.5px)'
    }" >

    </div>
    <div>
        <h1> 
            This is product component
            <slot name="heading">
                <h3>Default</h3>
            </slot>
            <slot name="author">
                
            </slot>
            <slot name="pages">
                
            </slot>
            <slot></slot>
            <!-- {{bookTitle.title}}  -->
            <br>
            <!--REMEMBER!! no mastache syntax when we are binding an attribute -->
            <!-- <img :src="bookTitle.cover">
            <br>
            {{bookTitle.author}}
            <br> 
            <br>
            {{bookTitle.year}}
            <br> 
            <br>
            {{bookTitle.genre}}
            <br> 
            <br>
            {{bookTitle.pages}}
            <br> 
            <br>
            {{bookTitle.publisher}}
            <br> 
            <br>
            {{bookTitle.isbn}}  -->
             
        </h1>
    </div>
    
</template>

<script>
export default {
    // props:[
    //    'bookTitle'
    // ]
    props:['cover']
}
</script>
<style scoped>
h1{
    color: white;
    text-shadow: 3px 3px black;
}
img{
    width: 150px;
}
div{
    width: 300px;
    height: 400px;
    position:absolute;
    border-radius: 10%;
}
    
</style>