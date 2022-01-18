.<template>
  <main>
    <div class="container-60">
        <div  v-if="cards">
            <div class="row text-center pt-4">
                <Search 
                    @doSelect="getSearch($event)"
                />
                <!-- <div class="col">
                    <label class="text-light" for="level">Genre:</label>
                    <select v-model="selectValue" @change="getSearch" name="genre" id="select" class="ms-2 btn btn-primary">
                        <option value="All">All</option>
                        <option value="Rock">Rock</option>
                        <option value="Pop">Pop</option>
                        <option value="Jazz">Jazz</option>
                        <option value="Metal">Metal</option>
                    </select>
                </div> -->
            </div>
            <div class="row row-cols-5 px-5 pt-5">
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
        <div v-else class="row"> 
            <div class="col d-flex justify-content-center p-5">
                <h1 class="text-light">Loading . . .</h1>
            </div>
        </div>
    </div>
  </main>
</template>

<script>
import Card from './Card.vue';
import axios from 'axios';
import Search from './Search.vue';

export default {
    name: 'Main',
    components: {
        Card,
        Search,
    },
    data() {
        return {
            cards: null,
            genre: null,
            selectValue: 'All',
            selectArtist: 'All',
        }
    },
    mounted() {
        setTimeout(() => {
            this.getCards();
        }, 2000);
    },
    methods: {
        getCards() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                this.cards = result.data.response;
                this.genre = result.data.response;
            })
            .catch((error) => {
                console.log(error);
            });
        },
        getSearch(text){
            this.cards = this.genre
            if (text !== 'All') {
                this.cards = this.genre.filter(element => element.genre === text);
            }
        },
    },
}
</script>

<style lang="scss" scoped>
    main {
        background-color: #1E2D3B;
        height: calc(100vh - 70px); 
        .container-60 {
            width: 60%;
            margin: auto;
        }
    }
</style>