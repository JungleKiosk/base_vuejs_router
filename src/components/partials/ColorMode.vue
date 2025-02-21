<template>
    <div class="theme-toggle">
        <button @click="toggleTheme" class="theme-button">
            {{ isDarkMode ? '🌞 Light Mode' : '🌙 Dark Mode' }}
        </button>
    </div>
</template>

<script>
export default {
    name: "ThemeToggle",
    data() {
        return {
            isDarkMode: false,
        };
    },
    mounted() {
        const currentTheme = localStorage.getItem("theme");
        if (currentTheme === "dark-mode") {
            this.isDarkMode = true;
            document.body.classList.add("dark-mode");
        } else {
            document.body.classList.add("light-mode");
        }
    },
    methods: {
        toggleTheme() {
            this.isDarkMode = !this.isDarkMode;
            if (this.isDarkMode) {
                document.body.classList.remove("light-mode");
                document.body.classList.add("dark-mode");
                localStorage.setItem("theme", "dark-mode");
            } else {
                document.body.classList.remove("dark-mode");
                document.body.classList.add("light-mode");
                localStorage.setItem("theme", "light-mode");
            }
        },
    },
};
</script>

<style scoped>
.theme-button {
    background-color: #2c3e50;
    color: #ecf0f1;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

.theme-button:hover {
    background-color: #34495e;
}

body.dark-mode .theme-button {
    background-color: #ecf0f1;
    color: #2c3e50;
}

body.dark-mode .theme-button:hover {
    background-color: #bdc3c7;
}
</style>