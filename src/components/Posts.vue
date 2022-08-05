<script>

    import Paragraph from './Paragraph.vue'
    export default {
        components: {
            Paragraph
        },
        props: [
            'postDate',
            'postContent'
        ],
    }
</script>

<template>
    <div class="flex rounded-lg border-2 border-gray-700 dark:border-slate-800 mt-2 w-full h-fit p-2 lg:p-3 flex-col">
        <div class="text-base lg:text-sm font-archivo-narrow">
            <i class="opacity-50 fa-solid fa-clock"></i>
            {{ postDate }}
        </div>
        <div class="font-lato mt-1 p-1">
            <Paragraph
                v-for="pc in postContent"
                :pgItem="pc"
            />
        </div>
    </div>
</template>