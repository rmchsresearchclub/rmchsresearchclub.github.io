<script lang="ts">
    import { asset, resolve } from "$app/paths";
	import Icon from '@iconify/svelte';

    let { links }: { links: Array<Link> } = $props();
</script>

<script module>
    export interface Link {
        icon: string,
        title: string,
        href: string,
        isUrl: boolean
    }
</script>

<nav class="w-full flex flex-row gap-4">
    <!-- tailwind classes are larger than the fricking mount everest -->
    {#each links as link}
        <a class="rounded-full border border-black backdrop-blur-xs px-2 py-1 flex flex-row items-center gap-2 text-sm text-center lg:text-md lg:text-left" 
            href={link.isUrl ? link.href : resolve(link.href)}>
            <Icon icon={link.icon} class="inline size-8 lg:size-4" />
            <span class="hidden lg:inline">{link.title}</span>
        </a>    
    {/each}
    <!-- <a class="rounded-full border border-black backdrop-blur-xs px-2 py-1 flex flex-row items-center gap-2 text-sm text-center lg:text-md lg:text-left" 
        href={resolve("/academics")}>
        <Icon icon="ep:back" class="inline size-8 lg:size-4" />
        <span class="hidden lg:inline">Back to RMCHS Website</span>
    </a>
    <a class="rounded-full border border-black backdrop-blur-xs px-2 py-1 flex flex-row items-center gap-2 text-sm text-center lg:text-md lg:text-left" 
        href={resolve("/academics")}>
        <Icon icon="charm:graduate-cap" class="inline size-8 lg:size-4" />
        <span class="hidden lg:inline">List of Academics</span>
    </a> -->
</nav>