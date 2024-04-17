<h1 align="left">Hey 👋 What's up?</h1>

###

<p align="left">My name is ... and I'm a ..., from ....</p>

###

<h2 align="left">About me</h2>

###

<p align="left">✨ Creating bugs since ...<br>📚 I'm currently learning ...<br>🎯 Goals: ...<br>🎲 Fun fact: ...</p>

###

<h2 align="left">I code with</h2>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="javascript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" height="40" alt="typescript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" height="40" alt="react logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" height="40" alt="nextjs logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/storybook/storybook-original.svg" height="40" alt="storybook logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" height="40" alt="nodejs logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nestjs/nestjs-plain.svg" height="40" alt="nestjs logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jest/jest-plain.svg" height="40" alt="jest logo"  />
</div>

###


<a name="inicio"></a>

# Componentes

> Considerar que el código incluye bootstrap, jquery y owl-carousel pero en el CMS ya están incluidas esas librerías

# Tabla de Contenidos
- [Componentes](#componentes)
  - [Carrusel Estático](#carrusel-estático)
  - [Landing de Componentes](#landing-de-componentes)

## Carrusel Estatico
----
#### Código HTML

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Product Carousel with Owl Carousel</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.carousel.min.css" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.theme.default.min.css" rel="stylesheet">
  <style>
    :root {
      --gray-lighter: rgba(0, 0, 0, 0.1);
      --shadow: 0px 2px 7px var(--gray-lighter);
      --radius: 5px
    }

    .staticCarousel {
      font-family: Montserrat;
    }

    .staticCarousel .owl-carousel .item {
      align-items: inherit !important;
      margin: 4px
    }

    .staticCarousel .fixed-promo {
      height: calc(100% - 40px);
      box-shadow: var(--shadow);
    }

    .staticCarousel .fixed-promo picture img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      /* Asegura que la imagen cubra todo el espacio disponible sin deformarse */
    }

    .staticCarousel .card img {
      padding: 20px;
      max-width: 200px;
      height: auto;
      display: block;
      margin: 0 auto;
    }

    .staticCarousel .card {
      border: none;
      border-radius: var(--radius);
      height: 450px;
      box-sizing: border-box;
      display: flex;
      flex-direction: column;
      box-shadow: var(--shadow) !important;
    }

    .staticCarousel .card-img-top {
      border-top-left-radius: var(--radius);
      border-top-right-radius: var(--radius);
    }

    .staticCarousel .card-body {
      display: flex;
      flex-direction: column;
      height: 100%;
    }

    .staticCarousel .card-title {
      font-size: 18px;
      font-weight: 500;
      width: 100%;
      white-space: nowrap;
      text-overflow: ellipsis;
      overflow: hidden;
      color: #595959;
      text-align: center
    }

    .staticCarousel .card-text {
      font-size: 14px;
      font-weight: 600;
      color: #b2b2b2;
      text-align: center
    }

    .staticCarousel .card-price {
      font-size: 20px;
      font-weight: bold;
      margin-top: auto;
      color: #1788d3;
      text-align: center !important;
    }

    .staticCarousel .btn {
      background-color: #1788d3 !important;
      border-radius: var(--radius);
      color: #fff !important;
      font-weight: 600;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .staticCarousel .btn:hover {
      filter: brightness(calc(88 / 100));
      color: #fff;
    }

    .static-owl-carousel .owl-nav .owl-prev,
    .static-owl-carousel .owl-nav .owl-next {
      background-color: #C49A6C;
      border-radius: 50%;
      margin: 0 5px;
    }

    .static-owl-carousel .owl-next,
    .static-owl-carousel .owl-prev {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      display: block !important;
      height: 35px;
      width: 35px;
      background-color: #93d500 !important;
      border-radius: 50% !important;
    }

    .static-owl-carousel .owl-next {
      right: -20px;
    }

    .static-owl-carousel .owl-prev {
      left: -20px;
    }

    .static-owl-carousel .owl-nav i {
      color: white;
    }
  </style>
</head>
<body>
    <div class="landing">
        <section>
            <div class="container mt-4 staticCarousel">
          <div class="row">
            <div class="col-0 col-sm-5 col-md-4 col-lg-3">
              <div class="fixed-promo">
                <picture>
                  <source media="(min-width: 768px)" srcset="https://placehold.co/496x836?text=Promo+Image&font=open+sans" />
                  <img src="https://placehold.co/556x370?text=Promo+Image&font=open+sans" title="Banner" id="bannerEstatico" />
                </picture>
              </div>
            </div>
            <div class="col-12 col-sm-7 col-md-8 col-lg-9">
              <div class="owl-carousel owl-theme static-owl-carousel" id="fixed-carousel">
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+1&font=open+sans" alt="Product 1">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+2&font=open+sans" alt="Product 2">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+3&font=open+sans" alt="Product 3">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+4&font=open+sans" alt="Product 4">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+5&font=open+sans" alt="Product 5">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        </section>
    </div>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/owl.carousel.min.js"></script>
    <script>
$(document).ready(function () {
    // Función para ajustar la altura de las cards
    function adjustCardHeights() {
        var cards = $("#fixed-carousel .card");
        var maxHeight = 0;
        cards.css("height", "auto"); // Restablecer la altura

        // Esperar a que todas las imágenes carguen
        var images = cards.find("img");
        var imagesLoaded = 0;

        images.each(function () {
            $("<img>")
                .on("load", function () {
                    imagesLoaded++;
                    if (imagesLoaded >= images.length) {
                        // Una vez que todas las imágenes han cargado, calcular la altura máxima
                        cards.each(function () {
                            var cardHeight = $(this).outerHeight();
                            if (cardHeight > maxHeight) {
                                maxHeight = cardHeight;
                            }
                        });
                        // Aplicar la altura máxima a todas las cards
                        cards.outerHeight(maxHeight);
                    }
                })
                .attr("src", $(this).attr("src"));
        });

        // En caso de que todas las imágenes ya estén en caché y el evento load no se dispare
        if (images.length === 0) {
            cards.each(function () {
                var cardHeight = $(this).outerHeight();
                if (cardHeight > maxHeight) {
                    maxHeight = cardHeight;
                }
            });
            cards.outerHeight(maxHeight);
        }
    }

    // Inicializar el carrusel y ajustar las alturas
    $(".static-owl-carousel").owlCarousel({
        loop: true,
        margin: 10,
        nav: true,
        navText: ['<i class="fas fa-chevron-left"></i>', '<i class="fas fa-chevron-right"></i>'],
        responsive: {
            0: {
                items: 1,
            },
            768: {
                items: 2,
            },
            992: {
                items: 3,
            },
            1200: {
                items: 4,
            },
        },
    });

    // Llamar a adjustCardHeights después de la inicialización del carrusel para asegurar que las imágenes han cargado
    adjustCardHeights();
    $(window).resize(adjustCardHeights);
});

</script>
</body>
</html>

```

#### Imágen

| Desk |
| :------------: |
| ![](https://pandao.github.io/editor.md/examples/images/8.jpg) |

| Mobile |
| :------------: |
| ![](https://pandao.github.io/editor.md/examples/images/8.jpg) |

[========]

[![Top](https://img.shields.io/badge/-Volver%20al%20principio-blue?style=for-the-badge&logoColor=white)](#inicio)

[========]

[========]

[========]

### Carrusel Estatico
----
#### Código HTML

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Product Carousel with Owl Carousel</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.carousel.min.css" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.theme.default.min.css" rel="stylesheet">
  <style>
    :root {
      --gray-lighter: rgba(0, 0, 0, 0.1);
      --shadow: 0px 2px 7px var(--gray-lighter);
      --radius: 5px
    }

    .staticCarousel {
      font-family: Montserrat;
    }

    .staticCarousel .owl-carousel .item {
      align-items: inherit !important;
      margin: 4px
    }

    .staticCarousel .fixed-promo {
      height: calc(100% - 40px);
      box-shadow: var(--shadow);
    }

    .staticCarousel .fixed-promo picture img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      /* Asegura que la imagen cubra todo el espacio disponible sin deformarse */
    }

    .staticCarousel .card img {
      padding: 20px;
      max-width: 200px;
      height: auto;
      display: block;
      margin: 0 auto;
    }

    .staticCarousel .card {
      border: none;
      border-radius: var(--radius);
      height: 450px;
      box-sizing: border-box;
      display: flex;
      flex-direction: column;
      box-shadow: var(--shadow) !important;
    }

    .staticCarousel .card-img-top {
      border-top-left-radius: var(--radius);
      border-top-right-radius: var(--radius);
    }

    .staticCarousel .card-body {
      display: flex;
      flex-direction: column;
      height: 100%;
    }

    .staticCarousel .card-title {
      font-size: 18px;
      font-weight: 500;
      width: 100%;
      white-space: nowrap;
      text-overflow: ellipsis;
      overflow: hidden;
      color: #595959;
      text-align: center
    }

    .staticCarousel .card-text {
      font-size: 14px;
      font-weight: 600;
      color: #b2b2b2;
      text-align: center
    }

    .staticCarousel .card-price {
      font-size: 20px;
      font-weight: bold;
      margin-top: auto;
      color: #1788d3;
      text-align: center !important;
    }

    .staticCarousel .btn {
      background-color: #1788d3 !important;
      border-radius: var(--radius);
      color: #fff !important;
      font-weight: 600;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .staticCarousel .btn:hover {
      filter: brightness(calc(88 / 100));
      color: #fff;
    }

    .static-owl-carousel .owl-nav .owl-prev,
    .static-owl-carousel .owl-nav .owl-next {
      background-color: #C49A6C;
      border-radius: 50%;
      margin: 0 5px;
    }

    .static-owl-carousel .owl-next,
    .static-owl-carousel .owl-prev {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      display: block !important;
      height: 35px;
      width: 35px;
      background-color: #93d500 !important;
      border-radius: 50% !important;
    }

    .static-owl-carousel .owl-next {
      right: -20px;
    }

    .static-owl-carousel .owl-prev {
      left: -20px;
    }

    .static-owl-carousel .owl-nav i {
      color: white;
    }
  </style>
</head>
<body>
    <div class="landing">
        <section>
            <div class="container mt-4 staticCarousel">
          <div class="row">
            <div class="col-0 col-sm-5 col-md-4 col-lg-3">
              <div class="fixed-promo">
                <picture>
                  <source media="(min-width: 768px)" srcset="https://placehold.co/496x836?text=Promo+Image&font=open+sans" />
                  <img src="https://placehold.co/556x370?text=Promo+Image&font=open+sans" title="Banner" id="bannerEstatico" />
                </picture>
              </div>
            </div>
            <div class="col-12 col-sm-7 col-md-8 col-lg-9">
              <div class="owl-carousel owl-theme static-owl-carousel" id="fixed-carousel">
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+1&font=open+sans" alt="Product 1">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+2&font=open+sans" alt="Product 2">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+3&font=open+sans" alt="Product 3">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+4&font=open+sans" alt="Product 4">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
                <div class="item">
                  <div class="card">
                    <img class="card-img-top" src="https://placehold.co/275x275?text=Product+5&font=open+sans" alt="Product 5">
                    <div class="card-body">
                      <h5 class="card-title">Título</h5>
                      <p class="card-text">Descripción</p>
                      <p class="card-price">$ Precio</p>
                      <a href="#" class="btn">Ver más</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        </section>
    </div>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/owl.carousel.min.js"></script>
    <script>
$(document).ready(function () {
    // Función para ajustar la altura de las cards
    function adjustCardHeights() {
        var cards = $("#fixed-carousel .card");
        var maxHeight = 0;
        cards.css("height", "auto"); // Restablecer la altura

        // Esperar a que todas las imágenes carguen
        var images = cards.find("img");
        var imagesLoaded = 0;

        images.each(function () {
            $("<img>")
                .on("load", function () {
                    imagesLoaded++;
                    if (imagesLoaded >= images.length) {
                        // Una vez que todas las imágenes han cargado, calcular la altura máxima
                        cards.each(function () {
                            var cardHeight = $(this).outerHeight();
                            if (cardHeight > maxHeight) {
                                maxHeight = cardHeight;
                            }
                        });
                        // Aplicar la altura máxima a todas las cards
                        cards.outerHeight(maxHeight);
                    }
                })
                .attr("src", $(this).attr("src"));
        });

        // En caso de que todas las imágenes ya estén en caché y el evento load no se dispare
        if (images.length === 0) {
            cards.each(function () {
                var cardHeight = $(this).outerHeight();
                if (cardHeight > maxHeight) {
                    maxHeight = cardHeight;
                }
            });
            cards.outerHeight(maxHeight);
        }
    }

    // Inicializar el carrusel y ajustar las alturas
    $(".static-owl-carousel").owlCarousel({
        loop: true,
        margin: 10,
        nav: true,
        navText: ['<i class="fas fa-chevron-left"></i>', '<i class="fas fa-chevron-right"></i>'],
        responsive: {
            0: {
                items: 1,
            },
            768: {
                items: 2,
            },
            992: {
                items: 3,
            },
            1200: {
                items: 4,
            },
        },
    });

    // Llamar a adjustCardHeights después de la inicialización del carrusel para asegurar que las imágenes han cargado
    adjustCardHeights();
    $(window).resize(adjustCardHeights);
});

</script>
</body>
</html>

```

#### Imágen

| Desk |
| :------------: |
| ![](https://pandao.github.io/editor.md/examples/images/8.jpg) |

| Mobile |
| :------------: |
| ![](https://pandao.github.io/editor.md/examples/images/8.jpg) |

[========]

[![Top](https://img.shields.io/badge/-Volver%20al%20principio-blue?style=for-the-badge&logoColor=white)](#inicio)

[========]

[========]

[========]

# Landing de componentes

[QA example](https://qas.ecommspf.com.mx/branding-jun22)

