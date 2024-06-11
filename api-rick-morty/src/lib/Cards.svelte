<script>
    export let caracter;
</script>
<dir> class="subcard">
    <img src={caracter.image} alt={caracter.name}/>
    <h2>{caracter.name}</h2>
    <h3>{caracter.species}</h3>
    <h3>{caracter.status}</h3>
</dir>