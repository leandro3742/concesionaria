<script>

    import Fiat from './Autos/Fiat/Fiat.svelte';
    import Volswagen from './Autos/Volswagen.svelte';
    import Chevrolet from './Autos/Chevrolet/Chevrolet.svelte';
    import Kia from './Autos/Kia.svelte';

    export let MARCA;
    export let ESTADO;

</script>

{#if MARCA === 'Fiat'}
    <Fiat {ESTADO} />    
{/if}

{#if MARCA === 'Volswagen'}
    <Volswagen {ESTADO} />    
{/if}

{#if MARCA === 'Chevrolet'}
    <Chevrolet {ESTADO} />   
{/if}

{#if MARCA === 'Kia'}
    <Kia {ESTADO} />   
{/if}