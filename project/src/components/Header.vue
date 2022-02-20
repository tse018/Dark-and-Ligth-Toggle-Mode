<template>
    <header class="header">
        <h1 class="header__title">
            {{ mode }} Mode
        </h1>

        <ToggleMode :mode="mode" @toggle="$emit('toggle')" />

        <nav class="header__nav">
            <div class="header__nav-link">
                Home
            </div>

            <div class="header__nav-link">
                About
            </div>

            <div class="header__nav-link">
                Portfolio
            </div>

            <div class="header__nav-link">
                Contact
            </div>
        </nav>
    </header>
</template>

<script>
import ToggleMode from '../components/ToggleMode.vue';

export default {
    props: ['mode'],
    components: {
        ToggleMode,
    },
};
</script>

<style>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 25px;
    height: 60px;
    background: whitesmoke;
    transition: background 0.3s ease-in-out;
}

.dark .header {
    background: #15202b;
}

.header__title {
    font-size: 32px;
    text-transform: uppercase;
    font-weight: 900;
}

.header__nav {
    display: flex;
    height: 60px;
}

.header__nav-link {
    display: flex;
    align-items: center;
    padding: 0 15px;
}

.header__nav-link:hover {
    background: gray;
}

.dark .header__nav-link:hover {
    background: #101520;
}

</style>
