<template>
    <div class="usersList">
        <div class="usersList-info">
            <p 
                class="usersList-info__user"
                @click="togglePopup"
            >
                {{ usersList.name }}
            </p>
            <p class="usersList-info__user">
                {{ usersList.registrations }}
            </p>
        </div>
        <div class="usersList-block">
            <ButtonBasic 
                label="Удалить анкету" 
                class="usersList-block__button"
            /> 
            <ButtonBasic 
                label="Добавить в ЧС" 
                class="usersList-block__button"
            /> 
        </div>
    </div>
    <div 
        :class="['modal', {opened: isOpen}]"
        @click="togglePopup"
    >
        <div class="modal-background">
            <div class="modal-info">
                <img 
                    :src="usersList.image"
                    alt="user.image"
                    class="modal-info__image"
                >
                <div class="modal-info__name">
                    <p class="modal-info__name-text">
                        {{ usersList.firstName }}
                    </p>
                    <p class="modal-info__name-text">
                        {{ usersList.lastName }}
                    </p>
                </div>
                <div class="modal-info__name">
                    <p class="modal-info__name-text">
                        {{ usersList.region }}
                    </p> 
                    <p class="modal-info__name-text">
                        {{ usersList.city }}
                    </p>
                </div>
                <p class="modal-info__text">
                    Знак зодиака: {{ usersList.zodiac }}
                </p>
                <p class="modal-info__text">
                    Пол: {{ usersList.sex }}
                </p>
                <p class="modal-info__text">
                    Возраст: {{ usersList.age }} лет/года
                </p>
                <p class="modal-info__text">
                    Поиск зодиака: {{ usersList.searchZodiac }}
                </p>
                <p class="modal-info__text">
                    Магический число: {{ usersList.magicNumber }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
import ButtonBasic from '@/components/uikit/ButtonBasic.vue';

export default {
    name: 'UsersList',
    components: {
        ButtonBasic,
    },
    props: {
        usersList: {
            type: Object,
            required: true,
        },
    },
    data() {
        return {
            isOpen: false,
        };
    },
    methods: {
        togglePopup() {
            this.isOpen=!this.isOpen;
            if (this.isOpen) {
                document.querySelector('body').classList.add('disableScroll');
            } else {
                document.querySelector('body').classList.remove('disableScroll');
            }
        },
    },
};
</script>