<!-- 함수/이벤트 핸들러 할당/onMount() 실습 -->
<script>
	import { onMount } from 'svelte'
	let name = "Svelte Exercise 4";
	let isRed = false;

	/* onMount() : 현재 콤포넌트가 준비되면 콜백 함수의 내용을 실행함. 
	onMount() 전에는 컴포넌트 전체가 아직 준비가 안된것. 따라서
	box.addEventListener() 하면 box를 찾을 수 없기 때문에 box는 null이고
	addEventListener()도 당연히 제대로 인식 못함.
	*/
	onMount(() => {
		toggleBox()
	})

	function toggleBox() {
		const box = document.querySelector('.box2')
		box.addEventListener('click', ()=> { isRed = !isRed})
	}

	function enter() {
		name = 'enter'
	}
	function leave(arg) {
		name = arg
	}
</script>

<h1>Hello {name}!</h1>

<div class="box2" style="background-color: {isRed ? 'blue': 'green'}">Box2</div>
<div class="box" style="background-color: {isRed ? 'red': 'orange'}"
	on:click={()=> { isRed = !isRed}}
	on:mouseenter={enter}
	on:mouseleave={()=>{ leave('leave2')}}>Box!</div>

<style>
	.box {
		width: 300px;
		height: 150px;
		background-color: orange;
	}
</style>