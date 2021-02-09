<!-- 스토어 이용한 Todo 간단 예제
  양방향 바인딩을(아래 참고) 이용하면 store 이용 안해도 되긴 함.
  <TodoItem bind:todos={todos} {todo}/> -->

<script>
  import TodoItem from './TodoItem.svelte'
  import {todos} from './TodosStore'

  let title = HINT_STR
  const HINT_STR = '할일을 입력하세요'
  let id =0

  function createTodo() {
    $todos.push({id, title})
    $todos = $todos
    title = HINT_STR
    id += 1
  }

  function processFocus(text) {
    if (title != HINT_STR) return
    title = text
  }
</script>


<div>
  <input type="text" bind:value={title}
    on:keydown={ (e)=>{e.key == 'Enter' && createTodo()} }
    on:focus={ (e) => { processFocus('')} }
  />
  <button on:click={createTodo}>Create Todo</button>
</div>

{#each $todos as todo}
<!-- <TodoItem bind:todos={todos} {todo}/> // 양방향 바인딩을 통한 delete item 갱신 문제 해결법-->
<TodoItem {todos} {todo}/> <!-- sotre를 이용한 delete item 갱신 문제 해결법 -->
<!-- 주의: <TodoItem에 {$todos} 형태로 $붙여서 넘기면 쓰기가능한 store객체가
아니라 그냥 배열 데이터를 넘기는게 되어, 데이터 삭제 갱신이 안된다. -->
{/each}