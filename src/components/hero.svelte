<script context="module">
  import { fade, fly } from "svelte/transition";
  import { onMount } from "svelte";
  import { getLs, setLs } from "./utils.svelte";

  setLs("dark", true)

  let socialsIcon;
  let show = {
    socials: false,
  };
</script>

<div
  class="h-screen max-w-screen w-screen transition-colors fixed z-[-5]"
  class:bg-black={getLs("dark")}
  class:text-white={getLs("dark")}
>
  <div class="min-h-screen nav flex flex-col mx-3">
    <h1 class="text-7xl my-3 hover:underline w-fit font-light">&nbsp;</h1>
    <h1 class="text-7xl my-3 hover:underline w-fit font-light">
      <span class="text-3xl font-bold"> 1 </span>
      written
    </h1>
    <h1 class="text-7xl my-3 hover:underline w-fit font-light">
      <span class="text-3xl font-bold"> 2 </span>
      about
    </h1>
    <h1 class="text-7xl my-3 hover:underline w-fit font-light">
      <span class="text-3xl font-bold"> 3 </span>
      social
    </h1>
    <h1 class="text-7xl my-3 hover:underline w-fit font-light">
      <span class="text-3xl font-bold"> 4 </span>
      music
    </h1>
    <!-- <h1
      class="text-7xl my-3 hover:underline w-fit font-light select-none"
      on:click={() => {
        if (getLs("dark") === true) {
          setLs("dark", false);
        } else if (getLs("dark") === false) {
          setLs("dark", true);
        }
        console.log(getLs("dark"));
      }
      }
    >
      <span class="text-3xl font-bold"> 5 </span>
      <span class:hidden={getLs("dark")}>dark</span>
      <span class:hidden={getLs("dark")}>light</span>
      <span>mode?</span>
    </h1> -->
  </div>
</div>

<style>
  * {
    mix-blend-mode: difference;
  }
</style>
