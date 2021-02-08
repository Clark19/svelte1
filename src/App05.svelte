<script>
	let text = ''
</script>

<h1>{text}</h1>

<!-- 양방향 바인딩되게 번잡하게 작성법 -->
<input type='text' value={text} on:input={(e)=>{text = e.target.value}} />
<!-- input text 필드에 뭔가 입력되면 js 변수에 값 할당하는 방법
      on:input={(e)=>{text = e.target.value} 이런식으로 코딩 -->

<!-- 양방향 바이딩: bind:속성={} 이런식으로 사용. -->
<input type='text' bind:value={text} />
<button on:click={()=>{text = 'Park'}}> Click </button>


<style>

</style>