<script>
    import { toro, argo, uno_attractive, palio, uno } from '../Fiat/Datos.js';
    export let ESTADO;
    
    let arreglo = [toro, argo, uno_attractive, palio, uno];
    let nuevos = [];
    let usados = [];
    let i = 0;
    let a = 0;
    let b = 0; 

    while (i < arreglo.length){
        if (arreglo[i].Nuevo === true){ //EL AUTO ES 0KM
            nuevos[a] = arreglo[i];
            a++;
        }
        else{   //EL AUTO ES USADO
            usados[b] = arreglo[i];
            b++;
        }
        i++;
    }
    
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');
    a{
        border: grey;
    }
    .main{
        display: grid;
    }
    .autos{
        display: grid;
        justify-content: center;
    }
    .imagenes{
        margin: 0;
        padding:0;
        margin-top: 10px;    
        width: 250px;
        height: 150px;
        border: outset;
    }
    h2{
        font-family: 'Anton', sans-serif;
        display: flex;
        justify-content: center;
    }
    .descripcion{
        font-family: 'Anton', sans-serif;
        display: grid;
        justify-content: center;
        text-align: center;
    }

    @media screen and (min-width: 600px){
       h2{
           font-size: 35px;
       }
       h5{
           font-size: 25px;
           color: grey;
       }
       .main{
           grid-template-columns: 1fr 1fr 1fr;
       } 
       .imagenes{
           z-index: 50;
           position: relative;
           width: 350px;
           height: 250px;
       }
    }
</style>

<div class="main">
    
    {#if ESTADO === 'Todo'}
        
        {#each arreglo as i}
            <div class="autos">
                <a href={i.link} alt=""> <img class="imagenes" src={i.Fotos[0]} alt="" > </a>
                <h2>{i.Precio}</h2>
                <div class="descripcion">
                    <h5>Año: {i.Año}</h5>
                    <h5>{i.Nombre}</h5>
                </div>
            </div>    
        {/each}

    {/if}

    {#if ESTADO === 'Nuevos' }

        {#each nuevos as i}
            <div class="autos">
                <a href={i.link} alt=""> <img class="imagenes" src={i.Fotos[0]} alt="" > </a>
                <h2>{i.Precio}</h2>
                <div class="descripcion">
                    <h5>Año: {i.Año}</h5>
                    <h5>{i.Nombre}</h5>
                </div>
            </div>    
        {/each}

    {/if}

    {#if ESTADO === 'Usados'}

        {#each usados as i}
            <div class="autos">
                <a href={i.link} alt=""> <img class="imagenes" src={i.Fotos[0]} alt="" > </a>
                <h2>{i.Precio}</h2>
                <div class="descripcion">
                    <h5>Año: {i.Año}</h5>
                    <h5>{i.Nombre}</h5>
                </div>
            </div>    
        {/each}

    {/if}
</div>

