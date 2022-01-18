.<template>
  <header>
    <div class="row">
        <div class="logo col-12">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="logo spotify">
        </div>
    </div>
  </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style lang="scss" scoped>
    header {
        height: 70px;
        padding: 10px;
        background-color: #2E3A46;
        img {
            width: 50px;
        }
    }

</style>