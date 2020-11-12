<script>
  import features from "$features/index";
  import Layout from "sveature-layout";
  import { parseFeatures } from "sveature";
  export let promise = parseFeatures(features);
</script>

{#await promise then components}
  <Layout {components}>
    <h1>Design Library</h1>
    <p>Welcome to Sveature!</p>
  </Layout>
{/await}
