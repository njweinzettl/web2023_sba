<script>
    let character = '';

    fetch('https://rickandmortyapi.com/api/character')
    .then(res => res.json())
    .then(data => {
        console.log(data);
        character = data.results;
        character = character.splice(0,6);
    })
</script>

{#each character as char}
    <div class="card">
        <div class="image"></div>
            <img src= {char.image} alt ="rick & morty">
        <div class="info">
            <h1 class="name">{char.name}</h1>
            <h3 class="status"><div class="dead alive unknown"></div>{char.status}</h3>
            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{char.location.name}</a></h3>
        </div>
    </div>
{/each}

<style>
    .card{
        background:#333;
        height:240px;
        display:flex;    
        border-radius:20px;
        overflow: hidden; 
    }

    .image{
        width:100%;
        left:0;
        position: absolute;
    }

    .info{ padding: 10px 20px 15px 20px;}

    .dead, .alive, .unknown {
        width:10px;
        height:10px;
        border-radius:100%;
        margin-right:10px;
    }
    .dead{background:firebrick}

    .alive{background:green}

    .unknown{background:#777}

    h1, h3, a {
        font-family:sans-serif;
        color:white;
    }

    .status{
        display:flex;
        align-items:center;
    }

    .locationLabel{
        color:#777;
        font-size:16px;
        margin:0 0 5px;        
    }

    .location, a{
        font-size:16px;
        margin:10px 0px;
    }
</style>