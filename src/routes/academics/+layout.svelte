<script lang="ts">
    import type { LayoutProps } from './$types';
    import { asset, resolve } from "$app/paths";
	import Icon from '@iconify/svelte';

    let { data, children }: LayoutProps = $props();
</script>

<header class="fixed top-0 left-0 w-full">
    <nav class="w-full pr-2">
        <div class="m-4 flex flex-row gap-4">
            <!-- tailwind classes are larger than the fricking mount everest -->
            <a class="rounded-full border border-black backdrop-blur-xs px-2 py-1 flex flex-row items-center gap-2 text-sm text-center lg:text-md lg:text-left" 
                href={resolve("/academics")}>
                <Icon icon="ep:back" class="inline size-8 lg:size-4" />
                <span class="hidden lg:inline">Back to RMCHS Website</span>
            </a>
            <a class="rounded-full border border-black backdrop-blur-xs px-2 py-1 flex flex-row items-center gap-2 text-sm text-center lg:text-md lg:text-left" 
                href={resolve("/academics")}>
                <Icon icon="charm:graduate-cap" class="inline size-8 lg:size-4" />
                <span class="hidden lg:inline">List of Academics</span>
            </a>
        </div>
    </nav>
</header>

{@render children()}