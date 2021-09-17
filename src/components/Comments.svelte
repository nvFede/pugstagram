<script>
    export let comments = [];

    console.log(comments);

    function addComment(e) {
        const msg = e.target.text.value;
        if (msg.length > 3) {
            const message = {
                id: Date.now(),
                text: msg,
                username: "fede"
            }

            comments = [...comments, message];
            e.target.text.value = "";
        } 
    }

</script>
<style lang="scss">
  .comments {
    h3 {
      font-size: 14px;
      color: black;
      font-weight: bold;
      margin: 0;
      padding: 0;
    }
    span {
      font-size: 14px;
      margin: 0 0 0 0.5em;
      font-weight: normal;
      color: rgba(black, 0.9);
    }
    &__add {
      padding: 1em 1em 1em 1em;
      border-top: 1px solid rgba(219, 219, 219, 0.8);
      form {
        display: flex;
        justify-content: space-between;
        align-items: center;
      }
      input {
        border: solid 1px #e9e9e9;
        border-radius: 5px;
        color: #696969;
        border: 1px solid transparent;
        font-size: 12px;
        outline: none;
        width: 100%;
        display: flex;
      }
      button {
        border: none;
        color: #3897f0;
        font-size: 12px;
        outline: none;
        cursor: pointer;
      }
      label {
        display: none;
      }
    }
    &__content {
      padding: 0 1em 0.5em 1em;
    }
    &__users {
      margin: 0 0 0.5em 0;
      display: flex;
    }
  }


</style>



<div class="comments">
    <div class="comments__content">

        {#each comments as comment (comment.id) }
            <div class="comments__users">
                <h3>{comment.username}</h3>
                <span>{comment.text}</span>
            </div>
        {/each}
        <div class="comments__add">
            <form on:submit|preventDefault={addComment}>
                <input type="text"
                    id="text"
                    class="comments__input"
                    placeholder="Add comment...">
                <button type="submit">Post</button>
            </form>
        </div>
    </div>
</div>