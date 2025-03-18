<template>
    <div class="player">
        <div class="player-current">
            <i class="fa-solid fa-grip-vertical" id="grip"></i>
            <img src="../assets/img/miyo-listening.png" v-on:click="showSongDetails = !showSongDetails">
            <transition>
                <div class="player-informations" v-if="currentSong.playing">
                    <p>Tocando agora</p>
                    <p>{{ currentSong.name.replace("<br>", "") }}</p>
                </div>
            </transition>
        </div>
        <transition>
            <div v-if="showSongDetails">
                <div class="wrapper" v-on:click="showSongDetails = !showSongDetails"></div>
                <div class="player-select">
                    <div class="song" v-for="(song, index) in songs" :key="index">
                        <p v-html="song.name"></p>
                        <i class="fa-solid" :class="song.playing ? 'fa-circle-pause' : 'fa-circle-play'" v-on:click="togglePlay(song)"></i>
                    </div>
                </div>
            </div>            
        </transition>
    </div>
</template>
<script>
import saigoNoYume from "../assets/audios/最後の夢 (Saigo no Yume - O Último Sonho).mp3";
import soraGaKawatteMo from "../assets/audios/空が変わっても (Sora ga Kawatte mo - Mesmo que o céu mude).mp3";

export default {
    name: "playerComponent",
    data() {
        return {
            showSongDetails: false,
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
            currentVolume: 0,
            targetVolume: 0,
            currentSong: {
                name: "",
                src: "",
                playing: false,
                audio: null,
                volume: this.currentVolume
            }
        }
    },
    methods: {
        togglePlay: function (song) {

            if (this.currentSong.name != song.name && this.currentSong.audio != null) {
                this.currentSong.audio.pause();
            }

            if (this.currentSong.name != song.name) {
                this.currentSong.playing = false;
                this.currentSong = song;

                this.currentSong["audio"] = new Audio(this.currentSong.src);

                this.currentSong.audio.addEventListener("ended", () => {
                    this.currentSong.audio.pause();
                    this.currentSong.playing = false;
                });
            }
            
            if (this.currentSong.playing) {
                this.currentSong.audio.pause();
            } else {
                this.currentSong.audio.play();
            }

            this.currentSong.playing = !this.currentSong.playing;
        },
        makeControlDraggable: function (element) {
            let offsetX, offsetY, isDragging = false;

            element.style.position = "fixed"; // Garante que pode ser movido
            const grip = document.getElementById("grip");

            if (grip) {
                grip.style.cursor = "grab";

                // Início do arrasto (Mouse e Toque)
                function startDrag(event) {
                    const e = event.touches ? event.touches[0] : event; // Suporte a toque
                    const grabControl = e.target.closest("#grip");

                    if (grabControl) {
                        isDragging = true;
                        offsetX = e.clientX - element.getBoundingClientRect().left;
                        offsetY = e.clientY - element.getBoundingClientRect().top;
                        grip.style.cursor = "grabbing";
                        event.preventDefault(); // Evita rolagem no mobile
                    }
                }

                // Movimento do elemento
                function moveDrag(event) {
                    if (isDragging) {
                        const e = event.touches ? event.touches[0] : event;
                        element.style.left = e.clientX - offsetX + "px";
                        element.style.top = e.clientY - offsetY + "px";
                    }
                }

                // Fim do arrasto
                function stopDrag() {
                    isDragging = false;
                    grip.style.cursor = "grab";
                }

                // Eventos de Mouse
                grip.addEventListener("mousedown", startDrag);
                document.addEventListener("mousemove", moveDrag);
                document.addEventListener("mouseup", stopDrag);

                // Eventos de Toque (Mobile)
                grip.addEventListener("touchstart", startDrag, { passive: false });
                document.addEventListener("touchmove", moveDrag, { passive: false });
                document.addEventListener("touchend", stopDrag);
            }
        }

    },
    mounted: function () {
        this.makeControlDraggable(document.querySelector(".player"));
    }
}
</script>
<style scoped>
.player {
    position: fixed;
    top: 5rem;
    left: var(--space-10);
    z-index: 9999;
    background: var(--background-black-opacity);
    padding: var(--space-5);
    height: fit-content;
}

.player-current {
    display: flex;
    align-items: center;
    gap: var(--space-5);

    & img {
        width: 100px;
        height: 100px;
        min-width: 100px;
        min-height: 100px;
        max-width: 100px;
        max-height: 100px;
        border-radius: 50%;
        object-fit: cover;
        cursor: pointer;
    }
}

.player-informations {
    display: grid;
    gap: var(--space-3);

    & p {
        text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.8);
    }

    & p:first-child {
        animation: blink 4s ease-in-out infinite;
    }
}

@keyframes blink {
    0% {
        opacity: 1;
    }

    50% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

.player-select {
    background: var(--background-black-opacity);
    padding: var(--space-8);
    position: absolute;
    top: 110%;
    left: 0;
    display: grid;
    gap: var(--space-6);
    z-index: 2;
}

.song {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 250px;

    & i {
        cursor: pointer;
        transition: color 0.4s ease-in-out;

        &:hover {
            color: var(--blue);
        }
    }
}

@media (max-width: 768px) {
    .player-current {
        & img {
            width: 50px;
            height: 50px;
            min-width: 50px;
            min-height: 50px;
            max-width: 50px;
            max-height: 50px;
        }
    }
}
</style>