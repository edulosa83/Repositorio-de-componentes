<a name="inicio"></a>

## Carrusel con card estático

> Considerar que el código necesita Bootstrap, jQuery y owl-carousel pero en el CMS ya están incluidas esas librerías

#### Código JavaScript

```html
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

```
#### CSS

```html
<style>
  .staticCarousel {
    font-family: Montserrat;
  }

  .staticCarousel .owl-carousel .item {
    align-items: inherit !important;
    margin: 4px
  }

  .staticCarousel .fixed-promo {
    display: grid;
    height: calc(100% - 15px);
    box-shadow: var(--shadow);
  }

  .staticCarousel .fixed-promo img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    max-width: 100%;
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

```
#### Código HTML

```html
<div class="landing">
  <section>
    <div class="wrapper row">
      <div class="col-12">
        <div>
          <h2>Carrusel Card Statico</h2>
        </div>
      </div>
    </div>
    <div class="container mt-4 staticCarousel">
      <div class="row">
        <div class="col-0 col-sm-5 col-md-4 col-lg-3">
          <div class="fixed-promo">
            <picture>
              <source media="(min-width: 768px)" srcset="https://assets1.farmaciasanpablo.com.mx/documentos/_Desarrollo%20de%20Componentes/staticCarosuel-branding-clicsBienestar-desk@2x.jpg" />
			  <img src="https://assets1.farmaciasanpablo.com.mx/documentos/_Desarrollo%20de%20Componentes/staticCarosuel-branding-clicsBienestar-mobile@2x.jpg" title="Ofertas San Pablo Farmacia" id="slider-home-bau-banner02" />
              <!--<img src="https://placehold.co/600x400?text=Promo+Image&font=open+sans" alt="Ofertas San Pablo Farmacia" title="Ofertas San Pablo Farmacia" id="slider-home-bau-banner02" />-->
            </picture>
          </div>
        </div>
        <div class="col-12 col-sm-7 col-md-8 col-lg-9">
          <div class="owl-carousel owl-theme static-owl-carousel" id="fixed-carousel">
            <div class="item">
              <div class="card">
                <img class="card-img-top" src="https://hfprod.farmaciasanpablo.com.mx/sys-master-azureproductimages/h5b/h38/9457210654750/Fsp275Wx275H_Fsp800Wx800H_70002248_1foms4itp" alt="Placeholder image of EKOS Néctar para manos maracuyá">
                <div class="card-body">
                  <h5 class="card-title">One Touch Select Plus Flex Glucómetro + Lancetador + Tiras Reactivas</h5>
                  <p class="card-text">3 Piezas Paquete</p>
                  <p class="card-price">$371.00 MXN</p>
                  <a href="https://www.farmaciasanpablo.com.mx/equipo-y-botiquin/aparatos-de-medicion/glucometros/one-touch-select-plus-flex-glucometro-%2B-lancetador-%2B-tiras-reactivas/p/000000000070002248" class="btn">Ver más</a>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="card">
                <img class="card-img-top" src="https://hfprod.farmaciasanpablo.com.mx/sys-master-azureproductimages/h1a/hfd/9123257155614/Fsp480Wx480H_Fsp800Wx800H_70000594_1fnc524qs" alt="Placeholder image of EKOS Néctar para manos maracuyá">
                <div class="card-body">
                  <h5 class="card-title">La Roche Posay Effaclar Suero Facial Anti-Imperfecciones</h5>
                  <p class="card-text">30 ML Líquido Frasco Gotero</p>
                  <p class="card-price">$667.00 MXN</p>
                  <a href="https://www.farmaciasanpablo.com.mx/dermocosmeticos/facial/piel-grasa-facial/la-roche-posay-effaclar-suero-facial-anti-imperfecciones/p/000000000070000594" class="btn">Ver más</a>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="card">
                <img class="card-img-top" src="https://hfprod.farmaciasanpablo.com.mx/sys-master-azureproductimages/h99/h00/9126913736734/Fsp480Wx480H_Fsp800Wx800H_44930002_1fnc524qs" alt="Placeholder image">
                <div class="card-body">
                  <h5 class="card-title">Redoxon AOX Sabor Naranja</h5>
                  <p class="card-text">10 Tableta Tubo Ácido ascórbico 1000 MG</p>
                  <p class="card-price">$133.50 MXN</p>
                  <a href="https://www.farmaciasanpablo.com.mx/vitaminas-y-suplementos/vitaminicos/prevencion-de-resfriado/redoxon-aox-sabor-naranja/p/000000000044930002" class="btn">Ver más</a>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="card">
                <img class="card-img-top" src="https://hfprod.farmaciasanpablo.com.mx/sys-master-azureproductimages/hbf/h79/10466467938334/Fsp480Wx480H_Fsp800Wx800H_9150735_1g0durkqi" alt="Placeholder image">
                <div class="card-body">
                  <h5 class="card-title">La Roche Posay Effaclar Gel de Limpieza Facial Para Piel Grasa</h5>
                  <p class="card-text">400 ML Gel Envase</p>
                  <p class="card-price">$543.50 MXN</p>
                  <a href="https://www.farmaciasanpablo.com.mx/dermocosmeticos/facial/piel-grasa-facial/la-roche-posay-effaclar-gel-de-limpieza-facial-para-piel-grasa/p/000000000009150735" class="btn">Ver más</a>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="card">
                <img class="card-img-top" src="https://placehold.co/300x300?text=Product+1&amp;font=open+sans" alt="Placeholder image">
                <div class="card-body">
                  <h5 class="card-title">Redoxon AOX Sabor Naranja</h5>
                  <p class="card-text">10 Tableta Tubo Ácido ascórbico 1000 MG</p>
                  <p class="card-price">$133.50 MXN</p>
                  <a href="https://www.farmaciasanpablo.com.mx/vitaminas-y-suplementos/vitaminicos/prevencion-de-resfriado/redoxon-aox-sabor-naranja/p/000000000044930002" class="btn">Ver más</a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
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