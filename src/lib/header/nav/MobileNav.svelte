<script lang="ts">
    import { assets } from "$app/paths";
    import NavItem from "./NavItem.svelte";
    import { mobileNavOpen } from "$lib/libStore";
    import ThemeToggleButton from "$lib/general/ThemeToggleButton.svelte";

    let toggleMobileNav = function () {
        mobileNavOpen.update((n) => !n);
    };
</script>

<div class="fixed left-0 top-0 z-20 flex h-screen w-full flex-col items-center bg-white dark:bg-black gap-16 pt-16 { $mobileNavOpen ? 'flex' : 'hidden'}">

    <img src={ `${assets}/images/brand-logo/pairadux-logo.svg` } alt="" class="h-32 w-32 bg-blue-500 rounded-full">
    <ul class="flex flex-col items-center justify-center gap-16">
        <button
            type="button"
            on:click={toggleMobileNav}>
            <NavItem
                classes="text-3xl"
                href="/"
                label="Home" />
        </button>
        <button
            type="button"
            on:click={toggleMobileNav}>
            <NavItem
                classes="text-3xl"
                href="/resume"
                label="Resume" />
        </button>
        <button
            type="button"
            on:click={toggleMobileNav}>
            <NavItem
                classes="text-3xl"
                href="/projects"
                label="Projects" />
        </button>
        <button
            type="button"
            on:click={toggleMobileNav}>
            <NavItem
                classes="text-3xl"
                href="/about"
                label="About" />
        </button>
    </ul>
    <ThemeToggleButton />
</div>
