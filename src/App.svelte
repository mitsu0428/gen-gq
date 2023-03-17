<script>
  import ToDoInputForm from "./ToDoInputForm.svelte";
</script>

<main>
  <h1>Generate Good Question</h1>
  <p>「いい質問の仕方が分からない」</p>
  <p>「質問をするときに、自分の考えを整理することができない」</p>
  <p>「流行りのChatGPTのようなAIアプリで欲しい答えが返ってこない」</p>
  <p>GGQは、表示される入力フォームに沿って回答して「良い質問」を作れるよ。</p>
  <ToDoInputForm />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: left;
    height: 100vh;
  }
  p {
    margin: 0;
    padding: 0;
  }
</style>
