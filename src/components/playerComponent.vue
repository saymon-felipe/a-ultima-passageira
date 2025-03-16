<template>
    <div class="player">
        <div class="player-current">
            <img src="../assets/img/miyo-listening.png">
            <div class="player-informations">
                <p>Tocando agora</p>
                <p>{{ currentSong.name }}</p>
            </div>
        </div>
        <div class="player-select">
            <div class="song" v-for="(song, index) in songs" :key="index">
                <p v-html="song.name"></p>
                <i class="fa-solid fa-circle-play"></i>
            </div>
        </div>
    </div>
</template>
<script>
import saigoNoYume from "../assets/audios/最後の夢 (Saigo no Yume - O Último Sonho).mp3";
import soraGaKawatteMo from "../assets/audios/空が変わっても (Sora ga Kawatte mo - Mesmo que o céu mude).mp3";

export default {
    name: "playerComponent",
    data() {
        return {
            songs: [
                {
                    name: "最後の夢 <br> (O Último Sonho)",
                    src: saigoNoYume,
                    playing: false
                },
                {
                    name: "空が変わっても <br> (Mesmo que o céu mude)",
                    src: soraGaKawatteMo,
                    playing: false
                }
            ],
            currentSong: {
                name: "",
                src: "",
                playing: false
            }
        }
    }
}
</script>