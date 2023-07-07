<template>
    <div class="text-center ">
        <h1 class="text-4xl font-bold">THis is slot Example</h1>
    
<!-- ------------------------------------------------------------------ -->
<h1 class="mt-4 font-bold">Example 1 Slot ..</h1>
        <h1>Example 1</h1>
    <HelloSlot>
        <h1>Hello Harry</h1>
    </HelloSlot>
<!-- ------------------------------------------------------------------ -->
        <h1 class="mt-4 font-bold">Example 2 default slot ..</h1>
    <!-- Here no content is provided -->
    <HelloSlot></HelloSlot>

<!-- ------------------------------------------------------------------- -->
        <h1 class="mt-4 font-bold">Example 3 Named Slot ..</h1>
        <!-- Here is the named slot -->
        <BaseLayout>
            <h1>Hello i am default</h1>

            <template v-slot:header>
                <p>This is Header</p>
            </template>

            <template #main>
                <p>This is main content with shorthand symbol #</p>
            </template>

            <template v-slot:footer>
                <p>This is footer</p>
            </template>
        
        </BaseLayout>

        <h1 class="mt-4 font-bold">Example 4 Scoped slot ..</h1>
        <HelloSlot v-slot="slotProps">
            <h1>Hello {{ slotProps.name }}</h1>
            <h1>You are {{ slotProps.age }} old</h1>
        </HelloSlot>


</div>
</template>

<script>

</script>