<template>
  <div class="app">
    <Navbar />
    <div class="container">
    <h1>Добавьте ваше учебное заведение</h1>
    <!-- <Input labelText="Введите ваш email:" v-model:field="mail" />
    <Input labelText="Введите код подтверждения:" v-model:field="pass" />
    <Button btnText="Отправить" type="sumbit" /> -->
    <Select class="vuzselect"
      defaultOption="Выберите учебное заведение"
      :options="vuzs.sort((a, b) => a.name.trim().localeCompare(b.name.trim()))"
      v-model:field="currentVuzId"
    />
    <Checkbox
      labelText="Общежитие:"
      v-model:field="currentIs_obsh"
      :checked="currentIs_obsh"
      inputName="inputName"
      inputId="inputId"
      labelfor="labelfor"
    />
    <Checkbox
      labelText="Государственный:"
      v-model:field="currentIs_gos"
      :checked="currentIs_gos"
      inputName="inputName"
      inputId="inputId"
      labelfor="labelfor"
    />
    <Checkbox
      labelText="Бюджетные места:"
      v-model:field="currentIs_budget"
      :checked="currentIs_budget"
      inputName="inputName"
      inputId="inputId"
      labelfor="labelfor"
    />
    <Checkbox
      labelText="Военная кафедра:"
      v-model:field="currentIs_voen"
      :checked="currentIs_voen"
      inputName="inputName"
      inputId="inputId"
      labelfor="labelfor"
    />
    <Checkbox
      labelText="Лицензия:"
      v-model:field="currentIs_license"
      :checked="currentIs_license"
      inputName="inputName"
      inputId="inputId"
      labelfor="labelfor"
    />
    <Input
      labelText="Количество программ обучения:"
      v-model:field="currentCount_programs"
      :value="currentCount_programs"
    />
    <Input
      labelText="Количество бюджетных мест:"
      v-model:field="currentCount_places"
      :value="currentCount_places"
    />
    <Input
      labelText="Количество платных мест:"
      v-model:field="currentCount_pay_places"
      :value="currentCount_pay_places"
    />
    <Input
      labelText="Проходной балл на бюджет:"
      v-model:field="currentCount_balls"
      :value="currentCount_balls"
    />
    <Input
      labelText="Проходной балл на платное обучение:"
      v-model:field="currentCount_pay_balls"
      :value="currentCount_pay_balls"
    />
    <Input
      labelText="Средняя стоимость обучения в год:"
      v-model:field="currentCount_min_price"
      :value="currentCount_min_price"
    />
    <!-- <Input
      labelText="Введите описание вашего учебного заведения:"
      v-model:field="currentShort_text"
      :value="currentShort_text"
    /> -->
    <Button btnText="Отправить" type="sumbit" @click="pushVuz" />

    <h2>Программы обучения</h2>
    <Select
      defaultOption="Выберите программу обучения"
      :options="
        programs.sort((a, b) => a.name.trim().localeCompare(b.name.trim()))
      "
      v-model:field="currentProgramId"
    />
    <Input
      labelText="Стоимость обучения в год:"
      v-model:field="currentPrice"
      :value="currentPrice"
    />
    <Input
      labelText="Проходной балл на бюджетной основе:"
      v-model:field="currentBall"
      :value="currentBall"
    />
    <Input
      labelText="Количество мест на бюджетной основе:"
      v-model:field="currentPlaces"
      :value="currentPlaces"
    />
    <Input
      labelText="Проходной балл на платной основе:"
      v-model:field="currentBall_pay"
      :value="currentBall_pay"
    />
    <Input
      labelText="Количество мест на платной основе:"
      v-model:field="currentPlaces_pay"
      :value="currentPlaces_pay"
    />
    <Checkbox
      labelText="После 11кл:"
      v-model:field="currentIs_11kl"
      :checked="currentIs_11kl"
    />
    <Checkbox
      labelText="После 9 кл:"
      v-model:field="currentIs_9kl"
      :checked="currentIs_9kl"
    />
    <Checkbox
      labelText="Очно:"
      v-model:field="currentIs_ochn"
      :checked="currentIs_ochn"
    />
    <Checkbox
      labelText="Заочно:"
      v-model:field="currentIs_zaoch"
      :checked="currentIs_zaoch"
    />
    <Checkbox
      labelText="Дистанционно:"
      v-model:field="currentIs_distance"
      :checked="currentIs_distance"
    />
    <Checkbox
      labelText="Очно/заочно:"
      v-model:field="currentIs_ochzaoch"
      :checked="currentIs_ochzaoch"
    />
    <Button btnText="Добавить" type="sumbit" @click="pushProg"/>

    </div>
   
    <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Input from "@/components/Input.vue";
import Button from "@/components/Button.vue";
import Footer from "@/components/Footer.vue";
import Checkbox from "./components/Checkbox.vue";
import Select from "@/components/Select.vue";

export default {
  components: {
    Footer,
    Navbar,
    Input,
    Button,
    Checkbox,
    Select,
  },

  data() {
    return {
      text: "",
      vuzs: [],
      mail: "",
      pass: "",
      count_programs: "",
      count_places: "",
      count_pay_places: "",
      count_balls: "",
      count_pay_balls: "",
      yearprice: "",
      short_text: "",
      is_obsh: 0,
      is_gos: 0,
      is_budget: 0,
      is_voen: 0,
      is_license: 0,
      currentVuzId: "",
      currentVuz: null,
      programs: [],
      currentProgramId: null,
      currentProgram: null,
      currentPrice: "",
      currentBall: "",
      currentBall_pay: "",
      currentPlaces: "",
      currentPlaces_pay: "",
      currentIs_11kl: 0,
      currentIs_9kl: 0,
      currentIs_ochn: 0,
      currentIs_zaoch: 0,
      currentIs_ochzaoch: 0,
      currentIs_distance: 0,
      currentIs_budget: 0,
      currentIs_gos: 0,
      currentIs_license: 0,
      currentIs_obsh: 0,
      currentIs_voen: 0,
      currentCount_balls: "",
      currentCount_pay_balls: "",
      currentCount_places: "",
      currentCount_min_price: "",
      currentCount_programs: "",
      currentShort_text: "",
      currentCount_pay_places: "",
      price: "",
      ball: "",
      places: "",
      ball_pay: "",
      places_pay: "",
      is_11kl: "",
      is_9kl: "",
      is_ochn: "",
      is_zaoch: "",
      is_ochzaoch: "",
      is_distance: "",
    };
  },

  methods: {

    async pushVuz() {
      await fetch("http://localhost:8080/vuzs", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          count_programs: this.count_programs,
          count_places: this.count_places,
          count_pay_places: this.count_pay_places,
          count_balls: this.count_balls,
          count_pay_balls: this.count_pay_balls,
          short_text: this.short_text,
          is_obsh: this.is_obsh,
          is_gos: this.is_gos,
          is_budget: this.is_budget,
          is_voen: this.is_voen,
          is_license: this.is_license,
        }),
      });
    },
    async pushProg() {
      await fetch("http://localhost:8080/programs", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          price: this.price,
          ball: this.ball,
          places: this.places,
          ball_pay: this.ball_pay,
          places_pay: this.places_pay,
          is_11kl: this.is_11kl,
          is_9kl: this.is_9kl,
          is_ochn: this.is_ochn,
          is_zaoch: this.is_zaoch,
          is_ochzaoch: this.is_ochzaoch,
          is_distance: this.is_distance,
        }),
      });
    },
  },
  
  watch: {

    async currentVuz() {
      let resp = await fetch(
        `http://localhost:8080/programs?vuzsId=${this.currentVuzId}`
      );
      this.programs = await resp.json();
      
      this.currentIs_budget = this.currentVuz?.is_budget;
      this.currentIs_gos = this.currentVuz?.is_gos;
      this.currentIs_license = this.currentVuz?.is_license;
      this.currentIs_obsh = this.currentVuz?.is_obsh;
      this.currentIs_voen = this.currentVuz?.is_voen;
      this.currentCount_balls = this.currentVuz?.count_balls;
      this.currentCount_pay_balls = this.currentVuz?.count_pay_balls;
      this.currentCount_places = this.currentVuz?.count_places;
      this.currentCount_min_price = this.currentVuz?.count_min_price;
      this.currentCount_programs = this.currentVuz?.count_programs;
      this.currentCount_pay_places = this.currentVuz?.count_pay_places;
      this.currentPrice = '';
      this.currentBall = '';
      this.currentBall_pay = '';
      this.currentPlaces = '';
      this.currentPlaces_pay ='';
      this.currentIs_11kl = 0;
      this.currentIs_9kl = 0;
      this.currentIs_ochn = 0;
      this.currentIs_zaoch = 0;
      this.currentIs_ochzaoch = 0;
      this.currentIs_distance = 0;
    },

    currentProgramId() {
      this.currentProgram = this.programs.find((program) => program.id == this.currentProgramId);
    },

    currentVuzId() {
      this.currentVuz = this.vuzs.find((vuz) => vuz.id == this.currentVuzId);
    },

    currentProgram() {
      this.currentPrice = this.currentProgram?.price;
      this.currentBall = this.currentProgram?.ball;
      this.currentBall_pay = this.currentProgram?.ball_pay;
      this.currentPlaces = this.currentProgram?.places;
      this.currentPlaces_pay = this.currentProgram?.places_pay;
      this.currentIs_11kl = this.currentProgram?.is_11kl;
      this.currentIs_9kl = this.currentProgram?.is_9kl;
      this.currentIs_ochn = this.currentProgram?.is_ochn;
      this.currentIs_zaoch = this.currentProgram?.is_zaoch;
      this.currentIs_ochzaoch = this.currentProgram?.is_ochzaoch;
      this.currentIs_distance = this.currentProgram?.is_distance;
    },
  },

  async mounted() {
    let resp = await fetch(
      "http://localhost:8080/vuzs?fields=id,name,text,is_obsh,is_budget,is_gos,is_license,is_voen,count_balls,count_pay_balls,count_places,count_min_price,count_programs,count_pay_places"
    );
    this.vuzs = await resp.json();
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
 max-height: 1180px;
 font-size: 18px; 
}
.vuzselect {
  width: 60%;
}
</style>

