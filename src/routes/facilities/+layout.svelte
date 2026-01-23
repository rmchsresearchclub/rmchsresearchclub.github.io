<svelte:head>
    <title>RMCHS Facilities</title>
</svelte:head>

<script lang="ts">
    import type { LayoutProps } from './$types';

    let { data, children }: LayoutProps = $props();
</script>

{@render children()}