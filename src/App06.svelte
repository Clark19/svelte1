<!-- Component 사용 실습: 컴포넌트 이름은 대문자로 작성해야 함. -->
<script>
  import Fruits from './Fruits.svelte'
  
    let fruits =['Apple', 'Banana', 'Cherry', 'Orange', 'Mango']
  </script>
  
  <!-- <Fruits fruits={fruits} /> // 속성(fruits)과 데이터의{fruits} 이름이 같을때 생략가능 -->
  <Fruits {fruits} />
  <Fruits {fruits} reverse/>
  <Fruits {fruits} slice='-2' />
  <Fruits {fruits} slice='0, 3' />
  
  <!-- <h2>Fruits</h2>
  <ul>
    {#each fruits as fruit}
      <li>{fruit}</li>
    {/each}
  </ul>
  
  <h2>Fruits Reverse</h2>
  <ul>
    {#each [...fruits].reverse() as fruit}
      <li>{fruit}</li>
    {/each}
  </ul>
  
  <h2>Fruits</h2>
  <ul>
    {#each fruits as fruit}
      <li>{fruit}</li>
    {/each}
  </ul>
  
  <h2>Fruits slice -2</h2>
  <ul>
    {#each fruits.slice(-2) as fruit}
      <li>{fruit}</li>
    {/each}
  </ul> -->
  
  
  <style>
  
  </style>