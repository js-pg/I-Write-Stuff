<script>
  import Hero from "./components/hero.svelte";
  import Written from "./components/written.svelte";
  import { fade } from "svelte/transition";

  let writtenNode;
  let showNav = false;
  //check if written is in viewport
  function checkWritten() {
    var writtenRect = writtenNode.getBoundingClientRect();
    var writtenTop = Math.abs(writtenRect.top);
	console.log(writtenTop);
	console.log("h:" + window.innerHeight);
    if (writtenTop < window.innerHeight - 100) {
      showNav = false;
    } else {
      showNav = true;
    }
  }

  //on scroll, check if written is in viewport
  window.addEventListener("scroll", () => {
    checkWritten();
    console.log(showNav);
  });
</script>

<div
  class="text-8xl w-screen font-bold fixed top-0 pl-[45px] left-0 z-[1000] bg-black text-white flex items-center justify-start h-[80px]" 
>
  <a class="transition-all mr-2" transition:fade class:text-2xl="{showNav}" href="/">zane{showNav.toString().replace(true, ":").replace(false, "")}</a>
	{#if showNav}
		<div class="flex items-center justify-center">
			<p transition:fade={{duration: 75, delay: 0.0}} class="mx-2 font-light text-xl">written</p><span transition:fade={{duration:75, delay:75}} class="text-2xl">•</span>
			<p transition:fade={{duration: 75, delay: 150}} class="mx-2 font-light text-xl">about</p><span transition:fade={{duration:75, delay:225}} class="text-2xl">•</span>
			<p transition:fade={{duration: 75, delay: 300}} class="mx-2 font-light text-xl">social</p><span transition:fade={{duration:75, delay:375}} class="text-2xl">•</span>
			<p transition:fade={{duration: 75, delay: 450}} class="mx-2 font-light text-xl">music</p>
		</div>
	{/if}
  </div
>
<Hero />
<div bind:this={writtenNode}>
  <Written />
</div>
