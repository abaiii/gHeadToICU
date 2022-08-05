<script>
    export default {
        props: [
            'barItem', // The name of the item
            'itemHref' // the href of the item
        ]
    }
</script>

<template>
    <a :href="itemHref" class="p-2"> {{barItem}} </a>
</template>