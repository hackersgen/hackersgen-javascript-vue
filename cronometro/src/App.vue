<template>
  <div id="app">
    <img class="img" src="./assets/cronometro.png" />
    <!-- inserire visualizzazione per il timer -->

    <div class="btns">
      <!-- aggiungere event listener al click al bottone, il click deve azionare il metodo play -->
      <button class="btn btn-margin">
        <!-- Inserire testo per il bottone che cambi dinamicamente da VIA a PAUSA quando è in corso un timer -->
        VIA
      </button>
      <!-- aggiungere event listener al click al bottone, il click deve azionare il metodo clear -->
      <button class="btn btn-margin">RESET</button>
    </div>
    <!-- aggiungere visualizzazione condizionale di questa sezione -->
    <div class="interval">
      <ul>
        <!-- bisogna creare un li per ogni interval in intervalList -->
        <li>
          <!-- visualizzare tempo trascorso -->
          TEMPO: 0
        </li>
      </ul>
      <!-- aggiungere event listener al click al bottone, il click deve azionare il metodo clearIntervalList -->
      <button class="btn">SVUOTA STORICO</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      sec: 0,
      min: 0,
      hour: 0,
      timer: null,
      intervalList: [],
    };
  },
  methods: {
    zfill(number) {
      // metodo che aggiunge un padding al numero e lo restituisce es: 1 --> 01 
    },
    play() {
      // aggiungere metodo per fare partire un intervallo con delay di 1 secondo e aggiungerlo alla variabile timer se il timer è uguale a null,
      // altrimenti rimuovere l'interval con clearInterval(this.timer) e resettare il timer a null
      // nel caso in cui il timer sia uguale a null bisogna chiamare il metodo this.playing() all'inizio sia dentro all'intervallo
      // nel caso in cui il timer sia null allora bisogna chiamare il metodo this.pause()
    },
    playing() {
      // devo aumentare i secondi in modo che 60 secondi mi aumentino i minuti di 1 e resettino i secondi
      // e che 60 minuti mi aumentino le ore di 1 resettando poi i minuti
    },
    pause() {
      // devo aggiungere l'orario formattato con `${this.zfill(this.hour)}:${this.zfill(this.min)}:${this.zfill(this.sec)}` a intervalList
    },
    clear() {
      // se il timer è diverso da null allora devo chiamare il metodo clearInterval(this.timer) e resettare il timer a null
      // devo poi settare i secondi, minuti, ore a zero e chiamare il metodo this.clearIntervalList()
    },
    clearIntervalList() {
      // bisogna svuotare la intervalList 
    },
  },
};
</script>

<style>
#app {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.img {
  width: 420px;
  height: 420px;
  padding-top: 100px;
}
.timer {
  color: #fff;
  font-size: 70px;
  margin-top: -210px;
}
.btns {
  margin-top: 155px;
  display: flex;
}
.btn {
  -webkit-user-select: none;
  -moz-user-select: none;
  width: 150px;
  background-color: #fff;
  font-size: 20px;
  border: none;
  border-radius: 5px;
  text-align: center;
  padding: 6px;
  cursor: pointer;
  transition: all ease-in-out 0.3s;
}
.btn-margin {
  margin: 0px 7px;
}
.btn:hover {
  opacity: 0.8;
}
.interval {
  color: #fff;
  flex: 1;
  width: 420px;
  margin-top: 15px;
}
.interval ul {
  text-align: center;
}
.interval ul li {
  list-style: none;
  background-color: rgb(70, 70, 70);
  padding: 15px;
  margin-bottom: 10px;
}
</style>
