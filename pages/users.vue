<template>
    <main>
        <div class="users container">
            <h1 class="users-heading">
                Список пользователей
            </h1>
            <div class="users-header">
                <p class="users-header__info">
                    ФИО
                </p>
                <p class="users-header__info">
                    Дата регистрации
                </p>
            </div>
            <UsersList 
                v-for="usersList in paginatedData"
                :key="usersList"
                :users-list="usersList"
            />
            <div class="users-buttons">
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
import UsersList from '@/components/usersList/UsersList.vue';
import cat from '@/assets/images/cat.png';

export default {
    name: 'UsersPage',
    components: {
        UsersList,
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
                    name: 'Жданов Николай Павлович',
                    registrations: '28.01.2023',
                    image: cat,
                    firstName: 'Николай',
                    lastName: 'Жданов',
                    zodiac: 'Рыбы',
                    sex: 'муж',
                    city: 'Ростов-на-Дону',
                    region: 'Ростовская область',
                    age: '32',
                    searchZodiac: 'Рак',
                    magicNumber: '42',
                },
                {
                    name: 'Жданов Николай Павлович',
                    registrations: '28.01.2023',
                    imageURL: 'йцуйцуйц',
                    firstName: 'Николай',
                    lastName: 'Жданов',
                    zodiac: 'Рыбы',
                    sex: 'муж',
                    city: 'Ростов-на-Дону',
                    region: 'Ростовская область',
                    age: '32',
                    searchZodiac: 'Рак',
                    magicNumber: '42',
                },
                {
                    name: 'Жданов Николай Павлович',
                    registrations: '28.01.2023',
                    imageURL: 'йцуйцуйц',
                    firstName: 'Николай',
                    lastName: 'Жданов',
                    zodiac: 'Рыбы',
                    sex: 'муж',
                    city: 'Ростов-на-Дону',
                    region: 'Ростовская область',
                    age: '32',
                    searchZodiac: 'Рак',
                    magicNumber: '42',
                },
                {
                    name: 'Жданов Николай Павлович',
                    registrations: '28.01.2023',
                    imageURL: 'йцуйцуйц',
                    firstName: 'Николай',
                    lastName: 'Жданов',
                    zodiac: 'Рыбы',
                    sex: 'муж',
                    city: 'Ростов-на-Дону',
                    region: 'Ростовская область',
                    age: '32',
                    searchZodiac: 'Рак',
                    magicNumber: '42',
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
