<template>
    <div>
        <div class="animate-spin h-5 w-5 mr-3">
            &larr; Back
        </div>
        <div class="w-6/12 border-2 border-[red] h-[7rem] mx-auto">
            <h1>{{data.name}}</h1>  
        </div>
    </div>
</template>


<script>
export default {
    props:['data']
}
</script>