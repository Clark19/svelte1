<script>
  // Props : 속성과 비슷한 거
  export let fruits
  export let reverse
  export let slice

  let computedFruits = []
  let name = ''

  if (reverse) {
    computedFruits = [...fruits].reverse()
    name = 'reverse'
  } else if (slice) {
    // 부모 콤포넌트로 부터 받은 데이터(Props) slice는 =>  '-2' 또는 '0, 3' 형식의 문자열 임
    // slice.split(',') => ['-2'], ['0', '3']
    // ...['2'] => '-2'
    // ...['0', '3'] => '0', '3'
    // [].slice(args) args 매개변수에 숫자가 문자형식으로 와도 작동됨.
    computedFruits = fruits.slice(...slice.split(','))
    name = `slice(${slice})`
  } else {
    computedFruits = fruits
  }
</script>


<h2>Fruits {name}</h2>
<ul>
	{#each computedFruits as fruit}
		<li>{fruit}</li>
	{/each}
</ul>