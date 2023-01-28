<template>
    <section class="layout">
        <header>
            <Navbar />
        </header>
        <slot />
    </section>
</template>

<script>
import Navbar from '@/components/uikit/Navbar.vue';

export default {
    name: 'LayoutsBlock',
    components: {
        Navbar,
    },
};
</script>