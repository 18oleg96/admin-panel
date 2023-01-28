<template>
    <div class="postItem">
        <p class="postItem-post">
            {{ postItem.post }}
        </p>
        <p class="postItem-post">
            {{ postItem.date }}
        </p>
    </div>
</template>

<script>

export default {
    name: 'PostItem',
    props: {
        postItem: {
            type: Object,
            required: true,
        },
    },
};
</script>