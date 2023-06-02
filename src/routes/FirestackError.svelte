<script>
  import { dev } from '$app/environment';

  export let error = null;
</script>

{#if $error}
  <div class="container p-4 is-flex is-flex-direction-column">
    <div class="content">
      <h1 class="title is-1 has-text-danger">{$error.message}</h1>
    </div>

    <div class="error">
      <pre class="trace">
      {dev ? $error.stack : ''}
    </pre>
    </div>
  </div>
{:else}
  <slot />
{/if}

<style>
  .error {
    border: 1px solid red;
  }
  .trace {
    font-family: monospace;
  }
</style>