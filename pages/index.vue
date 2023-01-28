<template>
    <main>
        <div class="blockForm container">
            <h1 class="blockForm-heading">
                Создать пост
            </h1>
            <form 
                id="form"
                class="blockForm-form"
                @submit.prevent="onSubmit"
            >
                <UiInput 
                    v-model="model.heading"
                    :model-value="model.heading"
                    type="text"
                    name="heading"
                    :required="true"
                    label="Заголовок"
                />
                <UiInput 
                    v-model="model.text"
                    :model-value="model.text"
                    type="text"
                    name="text"
                    :required="true"
                    label="Текст"
                />
                <UiInput 
                    v-model="model.activeLink"
                    :model-value="model.activeLink"
                    type="text"
                    name="activeLink"
                    :required="true"
                    label="Активная ссылка"
                />
                <label 
                    for="file-input"
                    class="label-input"
                >
                    Прикрепление фото/галереи фото, аудио/видео из вложения
                </label>
                <input
                    id="file-input"
                    type="file"
                    name="file"
                    required="true"
                    class="input"
                >
                <ButtonBasic 
                    label="Создать пост" 
                    class="blockForm-form__button"
                    type="submit"
                /> 
            </form>
        </div>
    </main>
</template>

<script>
import UiInput from '@/components/uikit/UiInput.vue';
import ButtonBasic from '@/components/uikit/ButtonBasic.vue';

export default {
    name: 'MainPage',
    components: {
        UiInput,
        ButtonBasic,
    },
    data() {
        return {
            model: {
                heading: '',
                text: '',
                activeLink: '',
            },
        };
    },
    methods: {
        onSubmit() {
            console.log(this.model);
        },
    },
};
</script>
