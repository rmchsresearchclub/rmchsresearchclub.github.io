<script lang="ts">
    let { className = undefined, title = "title", children = undefined, centerHeader = false, hasTopMargin = true  } = $props();
</script>

<article>
    <section class={"flex flex-col gap-4 w-full " + (hasTopMargin ? "mt-4 " : "") + (className ? className : "")}>
        <article class="border p-4 size-full">
            <h3 class={"text-2xl font-bold underline underline-offset-4 mb-8 mt-4" + (centerHeader ? " w-full text-center" : "")}>{title}</h3>
            <section>
                {@render children?.()}
            </section>
        </article>
    </section>
</article>