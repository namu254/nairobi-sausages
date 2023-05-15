<template>
    <div class="post-list">
        <div v-for="recipe in recipesData" :key="recipe.title" class="post">
            <div class="image-container">
                <img :src="`./post-image/${recipe.image}`" class="post-image" :alt="recipe.title" />
            </div>
            <div class="post-description">
                <p class="post-title">{{ recipe.title }}</p>
                <div class="post-tags">
                    <div v-for="tag in recipe.tags" class="post-tag" :style="getTagStyles(tag)">
                        {{ tag }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import recipesData from './recipes.json';
const tagStyles = {
    Soup: {
        backgroundColor: 'rgba(153, 64, 0, 0.14)',
        textColor: '#A25016',
        borderColor: 'rgba(153, 64, 0, 0.9)',
    },
    Homemade: {
        backgroundColor: 'rgba(244, 150, 82, 0.2)',
        textColor: '#F59E60',
        borderColor: 'rgba(244, 150, 82, 0.9)',
    },
    Banana: {
        backgroundColor: 'rgba(243, 208, 82, 0.2)',
        textColor: '#F3D052',
        borderColor: 'rgba(244, 208, 82, 0.9)',
    },
    Blueberry: {
        backgroundColor: 'rgba(82, 137, 244, 0.2)',
        textColor: '#6092F5',
        borderColor: 'rgba(82, 137, 244, 0.9)',
    },
    Cheesecake: {
        backgroundColor: 'rgba(95, 0, 153, 0.14)',
        textColor: '#6D16A2',
        borderColor: 'rgba(95, 0, 153, 0.9)',
    },
};
const defaultTagStyle = {
    backgroundColor: '#000000', // Fallback background color
    textColor: '#ffffff', // Fallback text color
    borderColor: '#000000', // Fallback border color
};


const getTagStyles = (tag) => {
    if (tag in tagStyles) {
        return {
            background: tagStyles[tag].backgroundColor,
            color: tagStyles[tag].textColor,
            borderColor: tagStyles[tag].borderColor,
        };
    } else {
        return defaultTagStyle;
    }
};

</script>

<style scoped lang="sass">


.post-list
    display: grid
    grid-template-columns: repeat(4, minmax(0, 1fr))
    gap: 20px
.post
    display: flex
    justify-content: stretch
    flex-direction: column
    background-color: #fff
    padding: 10px
    border-radius: 4px
.post-image
    border-radius: 1px
    cursor: pointer
    height: 300px
    width: 100%
    object-fit: cover
.post-tag
    padding: 3px 13px
    border-radius: 40px
    border: 1px solid
    cursor: pointer
.post-title
    font-family: 'Inter'
    font-style: normal
    cursor: pointer
    font-weight: 600
    font-size: 20px
    padding: 15px 0px 15px 0px
    line-height: 17px
    color: #000000
.post-tags
    display: flex
    gap: 10px

@media (max-width: 768px)
    
    .post-list
       display: grid
       grid-template-columns: repeat(2, minmax(0, 1fr))

@media (max-width: 1024px)
    .post-list
       display: grid
       grid-template-columns: repeat(2, minmax(0, 1fr))

    @media (max-width: 1280px)
    .post-list
       display: grid
       grid-template-columns: repeat(2, minmax(0, 1fr))   

@media (max-width: 640px)
    .post
        display: grid
        grid-template-columns: repeat(2, minmax(0, 1fr))
    .post-list
       display: grid
       grid-template-columns: repeat(1, minmax(0, 1fr))
        
    .post-image
        height: 100%
        object-fit: cover
        width: 100%
        
    .image-container
        border-radius: 1px
    .post-title
        padding: 0px
    .post-tags
        flex-wrap: wrap
    .post-description
        display: flex
        flex-direction: column
        justify-content: center
        padding: 0px 5px 0px 15px
        
</style>