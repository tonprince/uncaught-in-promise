<script>
  import { createBoundary } from './ErrorBoundary.js';
  import FirestackError from './FirestackError.svelte';

  let Boundary = createBoundary(FirestackError);

  async function getUsers() {
    return ['aaa', 'sss'];
  }
</script>

<Boundary>
  {#await getUsers() then users}
    {users.error()}
  {/await}
</Boundary>
