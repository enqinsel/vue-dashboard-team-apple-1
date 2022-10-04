<script setup>
const props = defineProps(['placeholder']);
const emit = defineEmits(['search']);

const keyupHandler = (e) => {
    emit('search', e.target.value);
}
</script>
    
<template>
    <div class="search">
        <div class="search__icon">
            <span class="material-symbols-outlined">search</span>
        </div>
        <input type="text" class="search__input" :placeholder="props.placeholder" @keyup.enter="keyupHandler">
    </div>
</template>
    
<style lang="scss">
.search {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;

    &__input {
        width: 100%;
        padding: 16px 20px 16px 52px;
        border-radius: 8px;
        background-color: var(--color-quaternary);
        border: none;

        &::placeholder {
            color: var(--color-text-light);
            font-size: 14px;
            font-family: var(--font-primary);
        }

        &:focus {
            outline: none;
        }
    }

    &__icon {
        position: absolute;
        left: 16px;
        color: var(--color-text);
        top: 50%;
        transform: translateY(-50%);
    }
}
</style>