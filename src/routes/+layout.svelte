<script lang="ts">
	import { ModeWatcher, toggleMode } from "mode-watcher";
	import "../app.css";
	import Button from "@/components/ui/button/button.svelte";
	import SunIcon from "@lucide/svelte/icons/sun";
	import MoonIcon from "@lucide/svelte/icons/moon";

	let { children } = $props();
</script>

<ModeWatcher />

<Button onclick={toggleMode} variant="outline" size="icon">
	<SunIcon
		class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 !transition-all dark:-rotate-90 dark:scale-0"
	/>
	<MoonIcon
		class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 !transition-all dark:rotate-0 dark:scale-100"
	/>
	<span class="sr-only">Toggle theme</span>
</Button>

{@render children()}
