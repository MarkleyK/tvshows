<template>
    <div class="card-group">
        <div class="card" style="width: 18rem;"  v-for="show in shows" v-bind:key = show.id >
            <img  v-bind:src="'https://image.tmdb.org/t/p/w300' + show.poster_path" class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{show.name}}</h5>
                <p class="card-text">{{show.overview}}</p>
               
           
            </div>
        </div>
    </div>
    
        
       


</template>

<script>

export default {
    name: 'Tvshows',
    props:['shows']
}
</script>