<script>
    export let charities;
</script>
<div>
    <h2>Daftar Charity</h2>
    {#if charities !== undefined}
        <ul>
            {#each charities as charity}
            <li>{charity}</li>
            {/each}
        </ul>
    {:else}
        <h5>Data Tidak Ditemukan</h5>
    {/if}
</div>