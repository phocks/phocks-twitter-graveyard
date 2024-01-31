<script lang="ts">
  import { onMount } from "svelte";

  // Function that returns a random number between 2 digits inclusive
  const random = (min: number, max: number) =>
    Math.floor(Math.random() * (max - min + 1) + min);

  let fullText = "";
  let fileNumber = random(1, 758);

  onMount(async () => {
    const tweets = await fetch(`tweets/${fileNumber}.json`).then((r) =>
      r.json(),
    );

    // Get random tweet from array
    const { tweet } = tweets[Math.floor(Math.random() * tweets.length)];

    console.log(tweet);

    // Get full text of tweet
    fullText = tweet.full_text;
  });
</script>

<main>
  {#if fullText !== ""}
    <div class="tweet-container">
      {fullText}
    </div>
  {/if}
</main>

<style lang="scss">
  .tweet-container {
    background-color: rgb(232, 237, 241);
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
    padding: 1rem;
    border: 1px solid #ccc;
    border-radius: 0.5rem;
    font-size: 1.5rem;
    line-height: 1.5;
  }
</style>
