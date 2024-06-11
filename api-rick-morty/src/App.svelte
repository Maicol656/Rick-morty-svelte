<script>
    import Cards from "./lib/Cards.svelte";
    let caracteres=[];
    let pagina=1;
    async function loadCharacters(){
        const response=await fetch("https://rickandmortyapi.com/api/character?page=%22+pagina"+pagina)
        const data= await response.json();
        console.log(data)
        caracteres=data.results;
    }
    loadCharacters();

    function siguiente(){
        pagina++;
        loadCharacters();
    }
    
    function anterior(){
        pagina--;
        loadCharacters();
    }
</script>

<h1> class="title">Rick and morty svelte</h1>
<h2> class="title">pagina: {pagina}</h2>

<div> class="contenedor">
    <div> calss="botonos">
        <button> class="boton" on:click={anterior} disabled=[pagina===1]>anterior</button>
        <button> class="boton" on:click={siguiente}</button>
    </div>
    <div> class="grid">
        {#each caracteres as caracter}
          <Cards {caracter}/>
          {/each}
    </div>
</div>