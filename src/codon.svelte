<script lang="ts">
  import gene_map from "./codon";
  let output = "";
  
  let inputValue: string = "";
  $: {
    let temp = "";
    let unknown: string = null;
    let cleansed = inputValue.replace(/[, ]/g, "").toUpperCase();
    for (let i = 0; i < cleansed.length; i += 3) {
      let key = cleansed.slice(i, i + 3);
      let new_char = gene_map[key];
      if (new_char === undefined) {
        unknown = key;
        break;
      }
      temp += new_char;
    }
    output = temp ? temp : "Start typing...";
    if (unknown !== null) {
      output = `Unknown pattern ${unknown}`;
    }
  }
</script>

<main class="flex-container">
  <div>
  <textarea
    bind:value={inputValue}
    placeholder="Enter codon sequence here"
    id="codon-input"
  />
  </div>
  <div class="output">
    {output}
  </div>
</main>


