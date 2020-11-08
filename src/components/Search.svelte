<script>
import Autos from './Autos.svelte';

let marca = false;
let estado = false;

function marcas(){
    marca = !marca;
    estado = false;
}

function estados(){
    marca = false;
    estado = !estado;
}

function Menu(variable){
    switch (variable) {
        //MODELO//
        case 'Todo':
            MARCA = 'Todo';
            marca = false;
            me_voy = false;
            break;
        case 'Fiat':
            MARCA = 'Fiat';
            marca = false;
            me_voy = false;
            break;
        case 'Volswagen':
            MARCA = 'Volswagen';
            marca = false;
            me_voy = false;
            break;
        case 'Chevrolet':
            MARCA = 'Chevrolet';
            marca = false;
            me_voy = false;
            break;
        case 'Kia':
            MARCA = 'Kia';
            marca = false;
            me_voy = false;
            break;
        //ESTADO//
        case 'Nuevos':
            ESTADO = 'Nuevos';
            estado = false;
            me_voy = false;
            break;
        case 'Usados':
            ESTADO = 'Usados';
            estado = false;
            me_voy = false;
            break;
        case 'Ambos':
            ESTADO = 'Todo';
            estado = false;
            me_voy = false;
            break;
    }
}
export let ESTADO = 'Todo';
export let MARCA = 'Todo';
let me_voy = false;
function guardar(){
    me_voy = true;
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inconsolata:wght@500&display=swap'); /*ESTE ES EL NUEVO*/
@import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');

h1{
    font-family: 'Inconsolata', monospace;  
    margin-top: 10px;
    text-align: center;
}

h2{
    font-family: 'Inconsolata', monospace;
}
a{
    text-decoration: none;
    transition-duration: 1s;
    font-family: 'Inconsolata', monospace;
}

button{
    outline:none;
    background-color: #5DADE2;
    font-family: 'Inconsolata', monospace;
}

/* ES EL CONTENEDOR PRINCIPAL */
.buscador{
    padding: 0;
    margin: 0;
    height: 200px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr; 
    grid-template-rows: 85px 2fr;
}

/* SON LOS CONTENEDORES DE LOS BUSCADORES */
.marcas, .estados{
    display: grid;
    justify-content: center;
    margin-left: 5px;
    padding: 5px;
}
 
.titulo{
    margin: 15px;
    position: sticky;
}

/* SON LOS BOTONES (TODOS) */
.botones{
    border: outset;
    padding-left: 10px;
    padding-right: 10px;
    transition-duration: 1s;
}
.botones:active{
    border: inherit;  
}

/* EL CONTENEDOR DEL BOTON BUSCAR */
.buscar{
    display: grid;
    justify-content: center;
    align-items: flex-end;
    margin-bottom: 5px;
    /* padding: 5px; */
}

/* EL BOTON BUSCAR */
.buscar-btn{
    color: white;
    background: #2b6cb0;
    padding: 2.5px;
    border-radius: 2.5px;
    /* border: outset; */
    transition-duration: 1s;
}
.buscar-btn:active{
    border: inherit;
    outline:none;
}

/* LOS CONTENEDORES DE CUANDO SE ACTIVAN LOS BOTONES */
.menu{
    margin-top: 10px;
    display: grid;
    justify-content: center;
    align-items: center;
}
.fondo{
    width: 100%;
    height: 100%;
    margin-top: 25px;
    justify-content: center;
    align-items: center;
    text-align: center;
}

@media screen and (max-width: 600px){
        
    h2{
        font-size: 15px;
    }
    a{
        font-size: 15px;
    }
    button{
      font-size: 15px;  
    }
    .menu{
        margin-top: 0px;
        position: relative;
    }
    
}

@media screen and (min-width: 600px){
    button{
        font-size: 20px;
    }    
    a:hover{
        font-size: 25px;
    }
}


</style>


<h1>Que es lo que estas buscando?</h1>
<div class="buscador">

    <div class="marcas">
        <h2 class="titulo">Marcas</h2>
        <button class="botones" on:click={marcas} >{MARCA}</button>
    </div>

    <div class="estados">
        <h2 class="titulo">Estados</h2>
        <button class="botones" on:click={estados} >{ESTADO}</button>
    </div>

    <div class="buscar">
       <button on:click={guardar} class="buscar-btn">Buscar</button>
    </div>
    
    <div class="menu">
    {#if marca === true}
            <div class="fondo">
                <a href="/" on:click={() => Menu('Todo')} alt="">Todo</a><br>
                <a href="/" on:click={() => Menu('Fiat')} alt="">Fiat</a><br>
                <a href="/" on:click={() => Menu('Volswagen')} alt="">Volswagen</a><br>
                <a href="/" on:click={() => Menu('Chevrolet')} alt="">Chevrolet</a><br>
                <a href="/" on:click={() => Menu('Kia')} alt="">Kia</a><br>
            </div>
    {/if}
    </div>
    
    <div class="menu">
    {#if estado === true}
            <div class="fondo">
                <a href="/" on:click={() => Menu('Ambos')} alt="">Todo</a><br>
                <a href="/" on:click={() => Menu('Nuevos')} alt="">Nuevos</a><br>
                <a href="/" on:click={() => Menu('Usados')} alt="">Usados</a>
            </div>
    {/if}
    </div>
</div>

{#if me_voy === true}
    <Autos {MARCA} {ESTADO} />
{/if}

<!-- {#if me_voy === false}
    <img src=banner2.jpg alt="">
{/if} -->
