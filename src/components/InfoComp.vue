<template lang="">
    <!-- <div>
        {{firstName}} {{lastName}} 
        {{objectData}}
    </div> -->
    <h1>This is the component</h1>
    <slot></slot>
</template>

<script>
export default {
    // tells us that data is being passed into component //passing strings
    // props:['firstName','lastName','objectData']
    //OR...
    props:{
        firstName: String,
        lastName: String,
        objectData: Object
    }
    
}
</script>

<style>

</style>