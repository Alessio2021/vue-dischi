.<template>
  <main>
    <div class="container-60">
        <div class="row row-cols-5 p-5">
            <Card 
                v-for="(card, index) in cards"
                :key="index"
                :img="card.poster"
                :title="card.title"
                :author="card.author"
                :year="card.year"
            />
        </div>
    </div>
  </main>
</template>

<script>
import Card from './Card.vue';
import axios from 'axios';

export default {
    name: 'Main',
    components: {
        Card,
    },
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
                this.cards = result.data.response;
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
            margin: auto;
        }
    }
</style>