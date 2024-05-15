<template>
<div :class="['quest-card', 'cat-' + quest.category]" :id="quest.id">
    <img :src="'../src/assets/images/questimg1.jpg'" :alt="quest.picture_alt_text" class="quest-image">
    <div class="quest-content">
        <p class="price text-center">{{ quest.price }} ₽</p>
        <h6 class="text-center">{{ quest.name }}</h6>
        <p class="text-center color4 quest_description">{{ quest.description }}</p>

        <div class="category">
            <p class="text-black quest_description filter">Категория:</p>
            <p class="color4 quest_description">{{ parseCategory(quest.category) }}</p>
        </div>

        <div class="duration">
            <p class="text-black quest_description filter">Время в пути:</p>
            <p class="color4 quest_description">{{ quest.duration }}</p>
        </div>

        <button @click="purchaseQuest(quest.id)" class="btn btn-primary primary-button questcard-button">Купить</button>
    </div>
</div>
</template>

<script>
export default {
    props: {
        quest: Object,
        parseCategory: Function,
        purchaseQuest: Function
    }
};
</script>  