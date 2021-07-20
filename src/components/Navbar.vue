<template>
  <div class="container">
      <div class="row align-items-center">
        <div class="col-md-2 col-4 pt10 pb10">
          <a href="/ekb"
            ><img
              src="https://test.uralstudent.ru/site_img/logo.png"
              class="img-fluid"
          /></a>
        </div>
        <div class="col-3 fs16">
          <a href="#city-popup" class="fancybox underline"
            >Екатеринбург <i class="fas fa-angle-down"></i
          ></a>
        </div>
        <div class="col-5 text-right d-md-none">
          <a href="#" class="toggle-menu fs20"><i class="fas fa-bars"></i></a>
        </div>
        <div class="col-md-7">
          <div class="d-flex">
            <div class="menu ml-auto">
              <ul>
                <li class="has-submenu">
                  <a href="/ekb/uchebnye-zavedeniya/vuzy">Высшее</a>
                  <ul>
                    <li>
                      <a href="/ekb/uchebnye-zavedeniya/vuzy">Все ВУЗы</a>
                    </li>

                    <li><a href="/ekb/professii-vuzy">Профессии ВУЗов</a></li>
                    <li>
                      <a href="/ekb/specialnosti-vuzy">Специальности ВУЗов</a>
                    </li>
                    <li><a href="/ekb/programmy-vuzy">Программы ВУЗов</a></li>
                  </ul>
                </li>

                <li class="has-submenu">
                  <a href="/ekb/uchebnye-zavedeniya/ssuzy">Профессиональное</a>
                  <ul>
                    <li>
                      <a href="/ekb/uchebnye-zavedeniya/ssuzy">Все СПО</a>
                    </li>

                    <li><a href="/ekb/professii-ssuzy">Профессии СПО</a></li>
                    <li>
                      <a href="/ekb/specialnosti-ssuzy">Специальности СПО</a>
                    </li>
                    <li><a href="/ekb/programmy-ssuzy">Программы СПО</a></li>
                  </ul>
                </li>

                <li class="has-submenu">
                  <a href="#" onclick="return false;">Другое</a>
                  <ul>
                    <li><a href="/ekb/novosti">Новости</a></li>
                    <li><a href="/ekb/statii">Статьи</a></li>
                  </ul>
                </li>
                <li class="d-md-none">
                  <form method="post" action="/search">
                    <div class="d-flex">
                      <input
                        placeholder="Найти..."
                        type="text"
                        value=""
                        name="search"
                        required=""
                      />
                      <button type="submit">
                        <i class="fa fa-search"></i>
                      </button>
                    </div>
                  </form>
                </li>
              </ul>
            </div>
            <div class="d-none d-md-block">
              <a
                href="#"
                class="toggle-search"
                data-toggle="modal"
                data-target="#searchModal"
                ><i class="fas fa-search"></i
              ></a>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.container{
    max-width: 1180px;
    margin: 0 auto;
}
</style>