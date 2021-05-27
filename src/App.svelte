<script lang="ts">
  import Codon from "./codon.svelte";
  import Gene from "./gene.svelte";
  import { Tabs, TabList, TabPanel, Tab } from "./tabs";
</script>

<Tabs>
  <TabList>
    <Tab>Codon Parser</Tab>
    <Tab>Gene Parser</Tab>
  </TabList>

  <TabPanel>
    <Codon/>
  </TabPanel>

  <TabPanel>
    <Gene />
  </TabPanel>

</Tabs>

<style>
</style>
