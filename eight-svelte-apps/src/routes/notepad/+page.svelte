<script>
  import { onMount} from 'svelte'
  import { writable } from 'svelte/store';

  const memo = writable (localStorage.getItem('memo') || '');

  onMount(() => {
    memo.set(localStorage.getItem('memo') || '');
  });
  function saveMemo() {
    localStorage.setItem('memo', $memo);
  }

  function clearMemo() {
    memo.set('');
    localStorage.removeItem('memo');
  }

</script>

<main>
  <h1>メモ帳</h1>
  <textarea bind:value={$memo} />
  <div class="container align-right">
    {#if $memo}
    <span>保存しました！</span> 
    {/if}
    <button id="clear" on:click={clearMemo}>削除</button>
    <button id="save" on:click={saveMemo}>保存</button>
  </div>
</main>

<style>
  main {
    width: 360px;
    margin: 16px auto 0;
  }

  h1 {
    margin: 0;
    font-size: 22px;
    text-align: center;
  }

  textarea {
    width: 100%;
    box-sizing: border-box;
    height: 160px;
    font-size: 16px;
    padding: 8px;
    margin-top: 8px;
  }

  button {
    padding: 4px 16px;
    cursor: pointer;
  }

  span {
    font-size: 14px;
    margin-right: auto;
    opacity: 0;
    transition: opacity 300ms;
  }

  .container {
    display: flex;
    align-items: flex-end;
    gap: 4px;
    margin-top: 8px;
  }

  .align-right {
    justify-content: flex-end;
  }


</style>
