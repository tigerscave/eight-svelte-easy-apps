<script context="module">
  //モジュールコンテキスト内で、localStorageの値を取得し、コンポーネント内で利用できるようにする
  import { writable } from 'svelte/store';

  export const memo = writable('');
</script>

<script>
  import { onMount } from 'svelte';
  let isSaved = false;

  onMount(() => {
    const storedMemo = localStorage.getItem('memo');
    if (storedMemo) {
      memo.set(storedMemo);
    }
  });

  function saveMemo() {
    localStorage.setItem('memo', $memo);
    isSaved = true;
    setTimeout(() => {
      isSaved = false;
    }, 1000);
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
    {#if $memo && isSaved}
    <span class="appear show">保存しました！</span> 
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
  .appear.show {
  opacity: 1;
}

</style>
