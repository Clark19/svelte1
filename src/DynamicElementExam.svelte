<!-- 동적으로 HTML(DOM) Element 삽입 하는 방법(Store 이용) 실습
Svelte는 정말 동적으로 Dom 엘리먼트를 생성하고 삽입하는건 아닌듯.
미리 만들어둔 Component를 스토어에 어떤 데이터가 있는지 없는지에 따라
출력 여부 결정짓는 방식인듯?
-->
<script>
	import DE from './DynamicElement.svelte'
	import { storeEle } from './DynamicElementStore.js'
	$storeEle = [ {id:0}, {id:1} ]

	function addItem() {
		let len = $storeEle.length;
		$storeEle[len] = {id: len}
	}
</script>

<button on:click={addItem}>Add an item</button>
{#each $storeEle as item}
<DE id={item.id}/>
{/each}