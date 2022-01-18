.<template>
<div class="col">
    <label class="text-light" for="level">Genre:</label>
    <select v-model="selectValue" @change="$emit('doSelect', selectValue)" name="genre" id="select" class="ms-2 btn btn-primary">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
</div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            selectValue: 'All',
        }
    }
}
</script>

<style>

</style>