<script>
  import features from "$features/index";
  import Layout from "sveature-layout";
  import { parseFeatures, getTargetFromPage } from "sveature";
  export let promise = parseFeatures(features);
  import { page } from "$app/stores";

  $: [component, feature] = getTargetFromPage($page);
</script>

{#await promise}
  <strong>Loading...</strong>
{:then components}
  <Layout {components} {component} {feature} />
{/await}
