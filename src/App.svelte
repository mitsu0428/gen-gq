<script>
  import ToDoInputForm from "./ToDoInputForm.svelte";
  import ToDoList from "./ToDoList.svelte";
  let nameEntered = false;

  let lastName = "";
  let firstName = "";

  $: fullName = lastName + " " + firstName;
  function handleSubmit() {
    if (lastName && firstName) {
      nameEntered = true;
    }
  }
</script>

<main>
  {#if nameEntered}
    <h1>Generate Good Question</h1>
    <p>{fullName}さん!</p>
    <ToDoInputForm userName={fullName} />
    <ToDoList />
  {:else}
    <h1>Generate Good Question</h1>
    <h3>名前を入力してください。</h3>
    <form on:submit|preventDefault={handleSubmit}>
      <div>
        <input bind:value={lastName} type="text" placeholder="姓" required />
      </div>
      <div>
        <input bind:value={firstName} type="text" placeholder="名" required />
      </div>
      <button type="submit">タスク管理を始める</button>
    </form>
  {/if}
</main>
