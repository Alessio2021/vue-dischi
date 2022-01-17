.<template>
    <div class="col text-center p-3">
        <div class="card p-3">
            <img :src="img" alt="">
            <h1 class="text-light fs-4 pt-2">{{title}}</h1>
            <h2 class="text-secondary fs-5">{{author}}</h2>
            <h2 class="text-secondary fs-5">{{year}}</h2>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    data() {
        return {
            
        }
    },
    props: [
        'img',
        'title',
        'author',
        'year',
    ]

}
</script>

<style lang="scss" scoped>
    .card {
        // width: 300px;
        height: 100%;
        background-color: #2E3A46;
        img {
            // width: 200px;
        }
    }
</style>