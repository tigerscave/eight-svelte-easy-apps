<script>

  let result = "?";
  let imageSrc = "";
  let imageAlt = "";
  const foods = [
    {name: "あさり汁", src: "/food-img/asarijiru.jpeg", alt: "あさり汁の画像"},
    {name: "野菜炒め",src: "/food-img/yasaiitame.jpeg",alt: "野菜炒めの画像"},
    {name: "ぱらぱらチャーハン",src: "/food-img/tya-han.jpeg",alt: "ぱらぱらチャーハンの画像"},
    {name: "塩ラーメン",src: "/food-img/sio-ramen.jpeg",alt: "塩ラーメンの画像"},
    {name: "小倉トースト",src: "/food-img/ogura-tosuto.jpeg",alt: "小倉トーストの画像"},
  ];

  function handleClick() {
    const n = Math.floor(Math.random() * foods.length);
    result = foods[n].name;
    imageSrc = foods[n].src;
    imageAlt = foods[n].alt;
  }
</script>

<section>
  <h1>今日の夜ご飯</h1>
  <p id="result">{result}</p>
  <p>
    <img class="food-img" src={imageSrc} alt={imageAlt} style="display: {imageSrc ? 'block' : 'none'};"/>
  </p>
</section>

<button class="green-button" on:click={handleClick} >食べ物を選ぶ</button>

<style>
  h1 {
    margin: 0;
    border-bottom: 2px solid green;
    font-weight: normal;
    padding: 8px 0;
  }

  p {
    margin: 0;
    font-weight: bold;
    font-size: 24px;
    padding: 24px 0;
  }

  .food-img {
    /* display: none; */
    width: 240px;
    height: 240px;
    margin: 0 auto;
  }

  section {
    height: 420px;
    border: 4px double green;
    text-align: center;
    color: green;
}
button {
  all: unset;
  width: 100%;
  background: green;
  border-radius: 8px;
  color: white;
  text-align: center;
  padding: 8px 0;
  margin-top: 16px;
  cursor: pointer;
  box-shadow: 0 4px gray;
  }

  button:active {
  transform: translateY(3px);
  }
</style>


