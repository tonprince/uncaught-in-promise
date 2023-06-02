<script>
  import { createBoundary } from './ErrorBoundary.js';
    import FirestackError from './FirestackError.svelte';
  
    let Boundary = createBoundary(FirestackError);
  
    function getUsers() {
      return ["aaa", "sss"];
    }
    </script>
  
  <Boundary>
    {#await getUsers() then users}
      {user.error()}
    {/await}
  </Boundary>