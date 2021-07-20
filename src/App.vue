<template>
  <div class="app">
       <Navbar />
       <h1>Добавьте ваше учебное заведение</h1>
       <Input labelText="Введите ваш email:"/>
       <Input labelText="Введите код подтверждения:"/>
       <Button btnText="Отправить" type="sumbit"/>
       <Input labelText="Введите название учебного заведения:"/>
       <Checkbox labelText="Общежитие:" />
       <Checkbox labelText="Государственный:" />
       <Checkbox labelText="Бюджетные места:" />
       <Checkbox labelText="Военная кафедра:" />
       <Checkbox labelText="Лицензия:" />
       <Input labelText="Количество программ обучения:"/>
       <Input labelText="Количество бюджетных мест:"/>
       <Input labelText="Количество платных мест:"/>
       <Input labelText="Проходной балл на бюджет:"/>
       <Input labelText="Проходной балл на платное обучение:"/>
       <Input labelText="Средняя стоимость обучения в год:"/>
       <Input labelText="Введите описание вашего учебного заведения:"/>
       
       <h2>Программы обучения</h2>
       <Input labelText="Наименование программы обучения:"/>
       <Input labelText="Стоимость обучения в год:"/>
       <Input labelText="Проходной балл на бюджетной основе:"/>
       <Input labelText="Количество мест на бюджетной основе:"/>
       <Input labelText="Проходной балл на платной основе:"/>
       <Input labelText="Количество мест на платной основе:"/>
       <Checkbox labelText="После 11кл:" />
       <Checkbox labelText="После 9 кл:" />
       <Checkbox labelText="Очно:" />
       <Checkbox labelText="Заочно:" />
       <Checkbox labelText="Дистанционно:" />
       <Checkbox labelText="Очно/заочно:" />
       <Button btnText="Добавить" type="sumbit"/>
       <Button btnText="Отправить" type="sumbit"/>
       <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Input from "@/components/Input.vue";
import Button from "@/components/Button.vue";
import Footer from "@/components/Footer.vue";
import Checkbox from './components/Checkbox.vue';

export default {
  components: {
    Footer,
    Navbar,
    Input,
    Button,
    Checkbox
  },

  data() {
    return {
      text: '',
    };
  },
  methods: {
    clickBtn() {
      console.log('BTN')
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>