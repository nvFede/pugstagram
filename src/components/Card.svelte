<script>
    import { writable} from 'svelte/store';
    import { count } from '../store/store.js';
    import { get } from 'svelte/store';

    import { blur } from 'svelte/transition';
    import Comments from './Comments.svelte';
	import Modal from './Modal.svelte';
    import Share from './Share.svelte';
    export let username;
    export let avatar;
    export let location;
    export let photo;
    export let comment;
    export let comments = [];

    let isModal = false;
    let like = false;
    let bookmark = false;

    function handleModal() {
        isModal = !isModal;
    }

    function handleLike() {
        like = !like;

        if (like) {
            count.update(n => n + 1);
        } else {
            count.update(n => n - 1);
        }

    }
 
</script>

<style lang="scss">
  .card {
    border: 1px solid rgba(219, 219, 219, 1);
    border-radius: 4px;
    background-color: white;
    margin: 0 0 2em 0;
    &__header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1em;
    }
    &__user {
        display: flex;
        align-items: center;
        justify-content: flex-end;
    }
    &__user img {
        width: 32px;
        height: 32px;
        border-radius: 50%;
    }
    &__user {
        h2 {
            margin: 0;
            padding: 0;
            font-size: 14px;
            font-weight: 600;
            margin: 0 0 0 1em;
            color: black;
            span {
                display: block;
                font-size: 12px;
                font-weight: normal;
                color: rgba(38, 38, 38, 0.7);
            }
        }
    }  
    &__photo {
        padding: 0;
        margin: 0;
    }
    &__photo img {
        width: 100%;
        height: auto;
    }
    &__photo figure {
        margin: 0;
        padding: 0;
        cursor: pointer;
    }
    &__settings i {
        cursor: pointer;
    }
    &__icons {
        padding: 1em;
        display: flex;
        justify-content: space-between;
        align-items: center;
        i {
            margin: 0 1em 0 0;
            cursor: pointer;
            font-size: 20px;
            &:last-child {
                margin: 0;
            }
        }
        .active-like {
            color: #bc1888;
            animation: bounce linear 0.8s;
            animation-iteration-count: 1;
            transform-origin: 20% 20%;
        }
        .active-bookmark {
            color: #f09433;
        }
    }
  
    &__description {
        padding: 0 1em 1em 1em;
        h3 {
            font-size: 14px;
            font-weight: bold;
            color: black;
        }
        span {
            font-size: 14px;
        }
    }
   
    
  }
  @keyframes bounce {
    0% {
      transform: translate(0px, 0px);
    }
    15% {
      transform: translate(0px, -25px);
    }
    30% {
      transform: translate(0px, 0px);
    }
    45% {
      transform: translate(0px, -15px);
    }
    60% {
      transform: translate(0px, 0px);
    }
    75% {
      transform: translate(0px, -5px);
    }
    100% {
      transform: translate(0px, 0px);
    }
  }
</style>

<div class="card">

    {#if isModal}
        <div transition:blur>
            <Modal>
                <Share on:click={handleModal} />
            </Modal>
        </div>
    {/if}

    <div class="card__container">
        <div class="card__header">
            <div class="card__user">
                <img src="{avatar}" alt="{username}">
                <h2>{username}
                <span>{location}</span>           
                </h2>
            </div>
            <div class="card__settings">
                <i class="fas fa-ellipsis-h"></i>
            </div>
        </div>

        <div class="card__photo">
            <figure on:dblclick={handleLike}>
                <img src="{photo}" alt="{username}">
            </figure>
        </div>

        <div class="card__icons">
            <div class="card__icons-left">
                <i class="fas fa-heart"
                    class:active-like={like} 
                    on:click="{handleLike}"
                 />
                <i class="fas fa-paper-plane" on:click={handleModal}/>
            </div>
            <div class="card__icons-right">
                <i class="fas fa-bookmark"
                    class:active-bookmark={bookmark}
                    on:click={() =>( bookmark =! bookmark ) } />
            </div>
        </div>

        <div class="card__description">
            <h3>{username}</h3>
            <span>{comment}</span>
        </div>

        <Comments comments={comments}  />
    </div>

</div>