<script>
  import Child from './Child.svelte'

  //Props
  export let name
</script>
<div>
  Parent
</div>

<Child {name} />