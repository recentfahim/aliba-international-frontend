<template>
    <div class="category-container">
        <ul class="category-list">
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-female"></i>
                    </div>
                    <div class="category-item-text">
                        Women's Fashion
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-tshirt"></i>
                    </div>
                    <div class="category-item-text">
                        Men's Fashion
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <div class="category-item-text">
                        Phones &amp; Telecommunications
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-laptop"></i>
                    </div>
                    <div class="category-item-text">
                        Computer, Office &amp; Security
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-camera"></i>
                    </div>
                    <div class="category-item-text">
                        Consumer Electronics
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-ring"></i>
                    </div>
                    <div class="category-item-text">
                        Jewelry &amp; Watches
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-couch"></i>
                    </div>
                    <div class="category-item-text">
                        Home, Pet &amp; Appliances
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-suitcase-rolling"></i>
                    </div>
                    <div class="category-item-text">
                        Bags &amp; Shoes
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-baby"></i>
                    </div>
                    <div class="category-item-text">
                        Toys, Kids &amp; Babies
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-basketball-ball"></i>
                    </div>
                    <div class="category-item-text">
                        Outdoor Fun &amp; Sports
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-walking"></i>
                    </div>
                    <div class="category-item-text">
                        Beauty, Health &amp; Hair
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-car"></i>
                    </div>
                    <div class="category-item-text">
                        Automobiles &amp; Motorcycles
                    </div>
                </div>
            </li>
            <li class="category-item">
                <div class="d-flex">
                    <div class="category-item-icon">
                        <i class="fas fa-tools"></i>
                    </div>
                    <div class="category-item-text">
                        Home Improvement &amp; Tools
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Category'
};
</script>

<style scoped>
.category-list {
    list-style: none;
}

.category-item {
    line-height: 35px;
}
.category-item-icon{
    width: 30px;
    text-align: center;
}

.category-item:hover{
    border-bottom: 1px solid #eaeaea;
    border-left: 2px solid #e2e2e2;
    color: #e62e04;
}
.category-item-text:hover{
    font-weight: 600;
}

.category-container {
    background-color: #ffffff;
    margin-top: -21px;
}
</style>