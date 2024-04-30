<a name="inicio"></a>

## Countdown Timer

> Considerar que el código necesita Bootstrap, jQuery y owl-carousel pero en el CMS ya están incluidas esas librerías

#### Código JavaScript

```html
<script>
  // Fijar la fecha por mes, dia, año, hora(s), minutos y segundos
  var countDownDate = new Date("Feb 22, 2024 15:10:00").getTime();

  function formatTime(i) {
    return i < 10 ? "0" + i : i;
  }

  var x = setInterval(function () {
    var now = new Date().getTime();

    var distance = countDownDate - now;

    var days = Math.floor(distance / (1000 * 60 * 60 * 24));
    var hours = Math.floor(
      (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
    );
    var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    var seconds = Math.floor((distance % (1000 * 60)) / 1000);

    document.getElementById("days").innerHTML = formatTime(days);
    document.getElementById("hours").innerHTML = formatTime(hours);
    document.getElementById("minutes").innerHTML = formatTime(minutes);
    document.getElementById("seconds").innerHTML = formatTime(seconds);

    // Si la cuenta atrás ha terminado, escribe un texto
    if (distance < 0) {
      clearInterval(x);
      document.getElementById("days").innerHTML = "00";
      document.getElementById("hours").innerHTML = "00";
      document.getElementById("minutes").innerHTML = "00";
      document.getElementById("seconds").innerHTML = "00";
      document.querySelector(".offer-banner span").innerHTML =
        "La oferta ha terminado";
    }
  }, 1000);
</script>

```
#### CSS

```html
<style>
  .offer-banner {
    font-family: "Roboto", sans-serif;
    background-color: #f8d7da;
    color: #721c24;
    padding: 10px 0;
    text-align: center;
  }
  .offer-banner .timer {
    font-weight: 500;
    display: inline-block;
    margin: 0 10px;
  }
  .offer-banner .timer .time-unit {
    display: inline-block;
    margin: 0 5px;
    text-align: center;
  }
  .offer-banner .timer .time-unit span.number {
    font-size: 18px;
    background-color: #721c24;
    color: #ffffff;
    padding: 2px 8px;
    border-radius: 4px;
    display: block;
  }
  .offer-banner .timer .time-unit span.text {
    background-color: transparent;
    color: #721c24;
    display: block;
    padding: 0;
    margin-top: 4px;
    font-size: 11px;
    font-weight: 300;
  }
  .offer-banner .btn-countdown {
    background-color: #dc3545;
    color: #ffffff;
    font-weight: 500;
    padding: 5px 20px;
    border-radius: 4px;
    text-decoration: none;
  }

  .ofertaUnica {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    margin-top: 15px;
  }

  @media (min-width: 992px) {
    .offer-banner {
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
</style>

```
#### Código HTML

```html
<div class="container-fluid offer-banner">
  <span>Hasta 60% OFF + 5% OFF Adicional + 3 MSI* Termina en:</span>
  <div class="ofertaUnica">
    <div class="timer">
      <div class="time-unit">
        <span id="days" class="number">00</span>
        <span class="text">Días</span>
      </div>
      <div class="time-unit">
        <span id="hours" class="number">00</span>
        <span class="text">Horas</span>
      </div>
      <div class="time-unit">
        <span id="minutes" class="number">00</span>
        <span class="text">Minutos</span>
      </div>
      <div class="time-unit">
        <span id="seconds" class="number">00</span>
        <span class="text">Segundos</span>
      </div>
    </div>
    <a href="#" class="btn-countdown" id="countdown-home-cta">Ver productos</a>
  </div>
</div>

```

#### Imágen

| Desk |
| :------------: |
| ![](https://raw.githubusercontent.com/edulosa83/Repositorio-de-componentes/main/Carrusel%20Estatico/_Evidencia/carruselEstaticoDesk.jpg?token=GHSAT0AAAAAACREDFZW7ZODACLTU4MASM6IZRAL6VA) |

| Mobile |
| :------------: |
| ![](https://raw.githubusercontent.com/edulosa83/Repositorio-de-componentes/main/Carrusel%20Estatico/_Evidencia/carruselEstaticoMobile.jpg?token=GHSAT0AAAAAACREDFZXEMHKMGPKWQOAPHPGZRAMBBA) |

[![Top](https://img.shields.io/badge/-Volver%20al%20principio-blue?style=for-the-badge&logoColor=white)](#inicio)

----

# Landing de componentes

[QA example](https://qas.ecommspf.com.mx/branding-jun22)