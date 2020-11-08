<script>
    import { toro, argo, uno_attractive, palio, uno } from './Datos.js';

    let auto = {};
    export let modelo;
    
    switch (modelo) {
        case "toro":
            auto = toro;
            break;
        case "argo":
            auto = argo;
            break;
        case "uno_attractive":
            auto = uno_attractive;
            break;
        case "palio":
            auto = palio;
            break;
        case "uno":
            auto = uno;
            break;
        default:
            break;
    }

    let i = 0;
    let a;
    a = i;
    
    function sumar(){
        if (a< auto.Fotos.length-1)
            a++;
        else
            a = 0;
    }
    function restar(){
        if (a == 0)
            a = auto.Fotos.length-1;
        else
            a--;
    }
    function elegir_foto (i){
        a = i;
        return a;
    }

</script>

<style>
    
    @import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');
    
    /* main{
        display: grid;
        justify-content: center;
        width: 100%;
    } */
    h1, h3{
        font-family: 'Anton', sans-serif;
    }

    h1{
        display: flex;
        justify-content: center;
        margin-top: 20px;
    }

    .titulo{
        color: grey;
    }

    .arriba{
        display: grid;
        justify-content: center;
        align-items: center;
        grid-template-columns: 5% 90% 5%;
    }

    .abajo{
        display: grid;
        justify-content: center;
    }
    
    .contenedor-imagen-grande{
        display: flex;
        justify-content: center;
    }

    .imagen-grande{
        display: grid;
        justify-content: center;
        align-items: center;
        border-radius: 10px;
    }

    .cuadros{
        display: flex;
        justify-content: center;
        align-items: center;
        border: outset;
    }

    .imagen-chica{
        cursor: pointer;
        display: grid;
        justify-content: center;
        align-items: center;
        width: 100%;
        border-radius: 10px;
    }
    
    /* .imagen-grande:hover {
        cursor: zoom-in;
    }
    .imagen-grande:active{
        width: 10px;
    } */

    @media screen and (max-width: 600px){
        .flecha{
            width: 25px;
            z-index: 10;
            position: absolute;
            cursor: pointer;
        }
        .arriba{
            height: 250px;
        }
        
        .abajo{
            
            grid-gap: 5px;
            grid-template-columns: repeat(5, 50px); 
        }

        .imagen-grande{          
            z-index: 0;
            position: relative;
            min-width: 250px; 
            max-width: 300px;
            max-height: 200px;
            min-height: 100px;
        }
        
        .cuadros{
            height: 40px;
            width: 50px;
        }

        .ficha{
            display: grid;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .texto{
            display: grid;
            grid-template-columns: 1fr 1fr ;
        }

        .titulo{
            color: grey;
            padding: 0;
            margin-bottom: 0;
        }
               
    }

    @media screen and (min-width: 601px){
        .flecha{
            cursor: pointer;
        }
        .imagen-grande{          
            max-height: 500px;
            min-height: 500px;
        }
        .abajo{
            margin-top: 10px;
            grid-gap: 15px;
            grid-template-columns: repeat(5, 100px); 
        }
        .cuadros{
            width: 100px;
            height: 80px;
        }

        .imagen-chica{
            width: 100px;
        }

        .texto{
            text-align: center;
            display: grid;
            width: 100%;
            grid-template-columns: repeat(3, 1fr); 
        }
        
    }
    
</style>

<main>
    <div class="fotos">
        <div class="arriba">
            <div on:click="{() => restar()}"> <img class="flecha" src=flecha_izquierda.png alt=""> </div>
            <div class="contenedor-imagen-grande">
                <img src={auto.Fotos[a]} alt="" class="imagen-grande">
            </div>
            <div on:click="{() => sumar()}" > <img class="flecha" src=flecha_derecha.png alt=""> </div>
        </div>
        <div class="abajo">
            {#each auto.Fotos as foto, i}
                <div class="cuadros" on:click="{() =>elegir_foto(i)}">
                   <img src={auto.Fotos[i]} alt="" class="imagen-chica">
                </div>
            {/each}
        </div>
    </div>
    <div class="ficha">
        <h1>{auto.Precio}</h1>
        <h1>Ficha tecnica</h1>
        <div class="texto">
            <div class="partes">
                <h3 class="titulo">Año</h3>
                <h3>{auto.Año}</h3>
            </div>

            <div class="partes">
                <h3 class="titulo">Puertas</h3>
                <h3>{auto.Puertas}</h3>
            </div>

            <div class="partes">
                <h3 class="titulo">Tipo de combustible</h3>
                <h3>{auto.TipoCombustible}</h3>
            </div>

            <div class="partes">
                <h3 class="titulo">Color</h3>
                <h3>{auto.Color}</h3>
            </div>

            <div class="partes">
                <h3 class="titulo">Motor</h3>
                <h3>{auto.Motor}</h3>
            </div>

            <div class="partes">
                <h3 class="titulo">Kilometros</h3>
                <h3>{auto.Kilometros}</h3>
            </div>

        </div>
    </div>
</main>

