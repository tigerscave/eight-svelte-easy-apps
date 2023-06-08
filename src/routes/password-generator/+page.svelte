<script>

    let numbersCheckbox = false;
    let symbolsCheckbox = false;
    let passwordLength = '8';
    let seed = '';

    const letters = 'abcdefghijklmnopqrstuvwxyz';
    const numbers = '0123456789';
    const symbols = '!@#$%^&*()'

    let password = '';

  function showPassword() {
    seed = letters + letters.toUpperCase();

    if (numbersCheckbox) {
      seed += numbers;
    }
    if (symbolsCheckbox) {
      seed += symbols;
    }
    password = generatePassword();
  }

  function handleClick() {
    showPassword();
  }
  function generatePassword() {
    let generatedPassword = '';
    for (let i = 0; i < passwordLength; i++) {
      const randomIndex = Math.floor(Math.random() * seed.length);
      generatedPassword += seed.charAt(randomIndex);
    }
    return generatedPassword;
  }

  $: showPassword();
</script>

<main>
  <p id="result">{password}</p> 
  <button id="btn"  on:click={handleClick} >パスワードを生成</button>
  <fieldset>
    <legend>オプション</legend>
    <label>
      長さ(<span id="password-length">{passwordLength}</span>)
      <input type="range" bind:value="{passwordLength}" min="8" max="24" />
    </label>
    <label>
      数字
      <input type="checkbox" bind:checked="{numbersCheckbox}" />
    </label>
    <label>
      記号
      <input type="checkbox" bind:checked="{symbolsCheckbox}" />
    </label>
  </fieldset>
</main>

<style>
  main {
    width: 380px;
    margin: 24px auto 0;
    box-shadow: 0 0 8px #999;
    border-radius: 8px;
    padding: 16px;
  }

  p {
    margin: 0;
    border: 1px solid #aaa;
    border-radius: 4px;
    font-family: "Courier New";
    text-align: center;
    padding: 12px 0;
  }

  input[type="range"] {
    background-color: yellowgreen;
  }

  button {
    all: unset;
    width: 100%;
    background: yellowgreen;
    border-radius: 8px;
    color: #fff;
    text-align: center;
    padding: 12px 0;
    margin-top: 16px;
    cursor: pointer;
  }

  button:hover {
    opacity: 0.6;
  }

  button:active {
    opacity: 0.4;
  }

  fieldset {
    border: 1px dashed #aaa;
    border-radius: 8px;
    padding: 16px;
    margin-top: 16px;
    display: flex;
    justify-content: space-betwen;
  }

  legend {
    padding: 0 8px;
  }

  #password-length {
    width: 24px;
    display: inline-block;
    text-align: center;
  }
</style>
