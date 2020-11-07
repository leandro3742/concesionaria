<script>
export let ESTADO;
</script>

{#if ESTADO === 'Todo'}
    <h1>Todo</h1>
{/if}

{#if ESTADO === 'Nuevos' }
    <h1>Nuevos</h1>
{/if}

{#if ESTADO === 'Usados'}
    <h1>Usados</h1>
{/if}