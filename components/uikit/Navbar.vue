<template>
    <div class="navbar">
        <NuxtLink 
            to="/"
            class="navbar-link"
        >
            Создание поста
        </NuxtLink>
        <NuxtLink 
            to="/historyPost"
            class="navbar-link"
        >
            История рекламных постов
        </NuxtLink>
        <NuxtLink 
            to="/users"
            class="navbar-link"
        >
            Список пользователей
        </NuxtLink>
    </div>
</template>

<script>

export default {
    name: 'NavBar',
};
</script>