<a name="inicio"></a>

## Product Box

> Considerar que el código necesita Bootstrap, jQuery y owl-carousel pero en el CMS ya están incluidas esas librerías

#### Código JavaScript

```html
<script>
	$(document).ready(function() {
		$("#slider-tradeBannerCarousel").owlCarousel({
			loop: true,
            margin: 0,
            autoplay: true,
            autoplayTimeout: 3000,
            autoplayHoverPause: true,
            stagePadding: 3,
            responsiveClass: true,
            dots: false,
            nav: false,
            navText: ["<i class='fas fa-chevron-left'></i>", "<i class='fas fa-chevron-right'></i>"],
            navClass: ["owl-prev", "owl-next"],
              responsive: {
                0: {
                  items: 1,
				  dots: true,
                },
                500: {
                  items: 2,
				  dots: true,
                },
                768: {
                  items: 3,
                  dots: true,
                },
                1000: {
                  items: 3,
                  dots: true,
                },
              },
            });
        });
</script>

```
#### CSS

```html
<style>
  .cardboxSlider {
    margin-right: 12px;
    cursor: grab;
    display: flex;
    flex-shrink: 0;
    height: 100%;
    width: 100%;
  }

  .cardbox {
    margin: 0 auto;
    width: 100%;
  }

  .cardboxContainer {
    margin: 5px;
    position: relative;
  }

  .cardbox-link {
    border-radius: 6px;
    display: flex;
    height: 250px;
    overflow: hidden;
    position: relative;
    text-align: center;
  }

  .cardbox-gradient {
    bottom: 0;
    position: absolute;
    width: 100%;
    z-index: 1;
    height: 124px;
    background: linear-gradient(0deg, rgb(8, 19, 48) 0%, rgba(8, 19, 48, 0.0001) 100%);
  }

  .cardboxSlider img,
  .cardbox-background {
    display: block;
    object-fit: cover;
    height: 100%;
    width: 100%;
    border-radius: var(--radius)
  }

  .cardbox-logo-text {
    align-items: center;
    bottom: 0;
    box-sizing: border-box;
    display: flex;
    justify-content: center;
    left: 0;
    padding: 16px;
    position: absolute;
    width: 100%;
    z-index: 1;
  }

  .cardbox-logo-text img.cardbox-logo {
    border-radius: 6px;
    display: flex;
    height: 70px;
    object-fit: contain;
    overflow: hidden;
    width: 70px;
    background: #FFFFFF;
    align-self: center;
    padding: 10px
  }

  #slider-tradeBannerCarousel .item .cardbox-gradient {
    border-radius: var(--radius)
  }

  #gelpharma {
    width: 160px;
    height: 80px;
    object-fit: cover;
    border-radius: 6px;
    background: #FFFFFF;
  }

  .cardbox-texts {
    color: #fff !important;
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    font-family: Montserrat;
  }

  .cardbox-texts span {
    color: #fff !important;
  }

  .cardbox-texts-line {
    display: block;
    margin-left: 16px;
    text-align: left;
  }

  .cardbox-texts-line--Titulo {
    font-size: 22px;
    font-weight: 600;
    line-height: 1.09;
  }

  .cardbox-texts-line--Subtitulo {
    font-size: 15px;
    letter-spacing: 0.4px;
    line-height: 1.11;
    margin-top: 4px;
    display: block;
    margin-left: 16px;
    text-align: left;
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
          <h2>Product Box</h2>
        </div>
        <div class="cardboxSlider">
          <div class="cardbox">
            <div class="main owl-carousel owl-theme" id="slider-tradeBannerCarousel">
              <!-- ====== Box 01 ====== -->
              <div class="item">
                <a href="#" class="cardbox-link">
                  <div class="cardboxContainer">
                    <div class="cardbox-gradient" aria-hidden="true"></div>
                    <picture>
                      <source media="(min-width: 1441px)" srcset="https://placehold.co/1000x600?text=Banner+1&font=open+sans" />
                      <source media="(min-width: 580px)" srcset="https://placehold.co/1000x600?text=Banner+1&font=open+sans" />
                      <img src="https://placehold.co/1000x600?text=Banner+1&font=open+sans" alt="Banner 1" title="Banner 1" id="productbox1" class="cardbox-background">
                    </picture>
                    <div class="cardbox-logo-text">
                      <img class="cardbox-logo" id="productbox-home-clubSalud-logo-box1" src="https://placehold.co/200x200?text=Image+1&font=open+sans" />
                      <div class="cardbox-texts">
                        <span class="cardbox-texts-line cardbox-texts-line--Titulo">Título</span>
                        <span class="cardbox-texts-line cardbox-texts-line--Subtitulo">Descripción</span>
                      </div>
                    </div>
                  </div>
                </a>
              </div>
              <!-- ====== Box 02 ====== -->
              <div class="item">
                <a href="#" class="cardbox-link">
                  <div class="cardboxContainer">
                    <div class="cardbox-gradient" aria-hidden="true"></div>
                    <picture>
                      <source media="(min-width: 1441px)" srcset="https://placehold.co/1000x600?text=Banner+2&font=open+sans" />
                      <source media="(min-width: 580px)" srcset="https://placehold.co/1000x600?text=Banner+2&font=open+sans" />
                      <img src="https://placehold.co/1000x600?text=Banner+2&font=open+sans" alt="Banner 2" title="Banner 2" id="productbox2" class="cardbox-background">
                    </picture>
                    <div class="cardbox-logo-text">
                      <img class="cardbox-logo" id="productbox-home-pronatur-background-box2" src="https://placehold.co/200x200?text=Image+2&font=open+sans" />
                      <div class="cardbox-texts">
                        <span class="cardbox-texts-line cardbox-texts-line--Titulo">Título</span>
                        <span class="cardbox-texts-line cardbox-texts-line--Subtitulo">Descripción</span>
                      </div>
                    </div>
                  </div>
                </a>
              </div>
              <!-- ====== Box 03 ====== -->
              <div class="item">
                <a href="#" class="cardbox-link">
                  <div class="cardboxContainer">
                    <div class="cardbox-gradient" aria-hidden="true"></div>
                    <picture>
                      <source media="(min-width: 1441px)" srcset="https://placehold.co/1000x600?text=Banner+3&font=open+sans" />
                      <source media="(min-width: 580px)" srcset="https://placehold.co/1000x600?text=Banner+3&font=open+sans" />
                      <img src="https://placehold.co/1000x600?text=Banner+3&font=open+sans" alt="Banner 3" title="Banner 3" id="productbox3" class="cardbox-background">
                    </picture>
                    <div class="cardbox-logo-text">
                      <img class="cardbox-logo" id="productbox-home-bebes-logo-box3" src="https://placehold.co/200x200?text=Image+3&font=open+sans" />
                      <div class="cardbox-texts">
                        <span class="cardbox-texts-line cardbox-texts-line--Titulo">Título</span>
                        <span class="cardbox-texts-line cardbox-texts-line--Subtitulo">Descripción</span>
                      </div>
                    </div>
                  </div>
                </a>
              </div>
              <!-- ====== Box 04 ====== -->
              <div class="item">
                <a href="#" class="cardbox-link">
                  <div class="cardboxContainer">
                    <div class="cardbox-gradient" aria-hidden="true"></div>
                    <picture>
                      <source media="(min-width: 1441px)" srcset="https://placehold.co/1000x600?text=Banner+4&font=open+sans" />
                      <source media="(min-width: 580px)" srcset="https://placehold.co/1000x600?text=Banner+4&font=open+sans" />
                      <img src="https://placehold.co/1000x600?text=Banner+4&font=open+sans" alt="Banner 4" title="Banner 4" id="productbox4" class="cardbox-background">
                    </picture>
                    <div class="cardbox-logo-text">
                      <img class="cardbox-logo" id="productbox-home-dermo-logo-box4" src="https://placehold.co/200x200?text=Image+4&font=open+sans" />
                      <div class="cardbox-texts">
                        <span class="cardbox-texts-line cardbox-texts-line--Titulo">Título</span>
                        <span class="cardbox-texts-line cardbox-texts-line--Subtitulo">Descripción</span>
                      </div>
                    </div>
                  </div>
                </a>
              </div>
              <!-- ====== Box 05 ====== -->
              <div class="item">
                <a href="#" class="cardbox-link">
                  <div class="cardboxContainer">
                    <div class="cardbox-gradient" aria-hidden="true"></div>
                    <picture>
                      <source media="(min-width: 1441px)" srcset="https://placehold.co/1000x600?text=Banner+5&font=open+sans" />
                      <source media="(min-width: 580px)" srcset="https://placehold.co/1000x600?text=Banner+5&font=open+sans" />
                      <img src="https://placehold.co/1000x600?text=Banner+5&font=open+sans" alt="Banner 5" title="Banner 5" id="productbox5" class="cardbox-background">
                    </picture>
                    <div class="cardbox-logo-text">
                      <img class="cardbox-logo" id="productbox-home-spn-logo-box5" src="https://placehold.co/200x200?text=Image+5&font=open+sans" />
                      <div class="cardbox-texts">
                        <span class="cardbox-texts-line cardbox-texts-line--Titulo">Título</span>
                        <span class="cardbox-texts-line cardbox-texts-line--Subtitulo">Descripción</span>
                      </div>
                    </div>
                  </div>
                </a>
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