<template>
    <div class="card my-2 p-0 box-shadow">
        <div class="row">
            <div class="col-md-12 my-2 d-flex">
                <div class="card-body">
                    <span class="nav-link2">選擇分類：</span>
                    <a 
                        class="nav-link2 mx-lg-2" 
                        href="#"  
                        :class="{ active: activeTag === '飯店' }" 
                        @click="filterProducts('飯店')"
                    >飯店</a>
                    <a 
                        class="nav-link2 mx-lg-2" 
                        href="#"  
                        :class="{ active: activeTag === '旅館' }" 
                        @click="filterProducts('旅館')"
                    >旅館</a>
                    <a 
                        class="nav-link2 mx-lg-2" 
                        href="#"  
                        :class="{ active: activeTag === '民宿' }" 
                        @click="filterProducts('民宿')"
                    >民宿</a>
                </div>
                <div>
                    <img style="height: 65px; width: auto;" src="/src/views/Layout/img/cat.png">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            activeTag: ''
        };
    },
    methods: {
        filterProducts(tag) {
            this.activeTag = tag;
            this.$emit('filter', tag); // 將點擊的分類傳遞給父組件
        }
    }
};
</script>

<style scoped>
/* 清除超連結預設底線、顏色 */
a {
    text-decoration: none;
    color: gray;
}

a.active {
    color: black;
}

.router-link-active {
    text-decoration: none;
}

@media (max-width: 767.98px) {
    a {
        padding: 8px;
    }
}
</style>
