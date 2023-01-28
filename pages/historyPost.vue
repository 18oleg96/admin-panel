<template>
    <main>
        <div class="history container">
            <h1 class="history-heading">
                История рекламных постов
            </h1>
            <div class="history-header">
                <p class="history-header__post">
                    Пост
                </p>
                <p class="history-header__post">
                    Дата поста
                </p>
            </div>
            <PostItem 
                v-for="postItem in paginatedData"
                :key="postItem"
                :post-item="postItem"
            />
            <div class="history-buttons">
                <button 
                    :disabled="pageNumber === 0" 
                    @click="prevPage"
                >
                    Предыдущая
                </button>
                <button 
                    :disabled="pageNumber >= pageCount -1" 
                    @click="nextPage"
                >
                    Следующая
                </button>
            </div>
        </div>
    </main>
</template>

<script>
import PostItem from '@/components/historyPost/PostItem.vue';

export default {
    name: 'HistoryPage',
    components: {
        PostItem,
    },
    data() {
        return {
            // номер страницы
            pageNumber: 0,
            // количество элементов на странице 
            // (для проверки поставил 3 и чтобы не занимать место в listData)
            size: 3,
            // элементы страницы
            listData: [
                {
                    post: 'q',
                    date: 'a',
                },
                {
                    post: 'qw',
                    date: 'as',
                },
                {
                    post: 'qwe',
                    date: 'asd',
                },
                {
                    post: 'qwer',
                    date: 'asdf',
                },
                {
                    post: 'qwert',
                    date: 'asdfg',
                },
                {
                    post: 'qwerty',
                    date: 'asdfgh',
                },
            ],
        };
    },
    computed: {
        // подсчет сколько есть страниц
        pageCount() {
            return Math.ceil(this.listData.length/this.size);
        },
        // отфильтрованные данные, которые отображаются.
        paginatedData() {
            const start = this.pageNumber * this.size;
            const end = start + this.size;
            
            return this.listData.slice(start, end); 
        },
    },
    methods: {
        // кнопки "Предыдущая" "Следующая"
        nextPage() {
            this.pageNumber++;
        },
        prevPage() {
            this.pageNumber--;
        },
    },
};
</script>
