<template>
    <button class="button"> 
        {{ label }}
    </button>
</template>

<script>

export default {
    name: 'ButtonBasic',
    props: {
        label: {
            type: String,
            required: true,
        },
    },
};
</script>