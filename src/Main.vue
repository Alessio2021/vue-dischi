.<template>
  <main>
    <div class="container-60">
        <div class="row row-cols-5">
            <div>
                <img 
                    src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" 
                    alt=""
                >
                <h1>New Jersey</h1>
                <h2>Bon Jovi</h2>
                <h2>1988</h2>
            </div>
        </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    data() {
        return {
            cards: [],

        }
    },
    mounted() {
        this.getCards();
    },
    methods: {
        getCards() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                this.cards = result.data.results;
            })
            .catch((error) => {
                console.log(error);
            });
        }
        
    },
}
</script>

<style lang="scss" scoped>
    main {
        .container-60 {
            width: 60%;
        }
    }
</style>