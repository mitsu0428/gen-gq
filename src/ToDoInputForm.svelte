<script>
  let text1 = "";
  let text2 = "";
  let text3 = "";

  function combineText() {
    const needTextDict = {
      text1: "[どんなツールを使っているか]",
      text2: "［特定の条件や環境はどんなものか］",
      text3: "[何をしたいかを具体的に]",
    };
    const combinedText = `${needTextDict.text1} ${text1} ${needTextDict.text2} ${text2} ${needTextDict.text3} ${text3}`;
    const combinedTextElement = document.createElement("p");
    combinedTextElement.textContent = combinedText;
    document
      .querySelector("[data-testid=result]")
      .appendChild(combinedTextElement);
  }
</script>

<div class="flex flex-col items-center justify-center h-screen">
  <h1 class="text-3xl font-bold mb-6">Text Combiner</h1>
  <div class="w-1/2">
    <div class="mb-4">
      <label for="text1" class="block font-medium mb-2"
        >使用している技術 :</label
      >
      <textarea
        id="text1"
        class="border rounded-lg p-2"
        placeholder="[どんなツールを使っているか]"
        bind:value={text1}
      />
    </div>
    <div class="mb-4">
      <label for="text2" class="block font-medium mb-2">制約条件:</label>
      <textarea
        id="text2"
        class="border rounded-lg p-2"
        placeholder="［特定の条件や環境はどんなものか］"
        bind:value={text2}
      />
    </div>
    <div class="mb-4">
      <label for="text3" class="block font-medium mb-2">何を:</label>
      <textarea
        id="text3"
        class="border rounded-lg p-2"
        placeholder="[何をしたいかを具体的に]"
        bind:value={text3}
      />
    </div>
    <button
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      on:click={combineText}
    >
      Combine
    </button>
    <h2 data-testid="result">この下に結果が表示されます。</h2>
  </div>
</div>

<style>
  div {
    width: 100%;
  }
  textarea {
    width: 100%;
    height: 100px;
  }
  button {
    border: none;
    padding: 16px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
  }
  button:hover {
    opacity: 0.8;
  }
</style>
