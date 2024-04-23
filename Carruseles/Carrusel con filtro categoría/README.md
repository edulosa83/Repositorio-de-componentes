<a name="inicio"></a>

## Carrusel con filtro categoría

> Considerar que el código necesita Bootstrap, jQuery y owl-carousel pero en el CMS ya están incluidas esas librerías

#### Código JavaScript

```html
<script>
$(document).ready(function() {
  function adjustCardHeights() {
    var maxHeight = 0;
    $("#filerOwlCarousel .card").each(function() {
      var cardHeight = $(this).height();
      maxHeight = Math.max(maxHeight, cardHeight);
    });
    $("#filerOwlCarousel .card").height(maxHeight);
  }

  adjustCardHeights();
  $(window).resize(function() {
    adjustCardHeights();
  });

  var items = $("#filerOwlCarousel .item").clone();

  function initOwlCarousel(filteredItemsCount) {
    var isMobile = window.innerWidth < 768;
    var loopSetting = filteredItemsCount > 5 || isMobile;

    $("#filerOwlCarousel").owlCarousel({
      loop: loopSetting,
      margin: 10,
      nav: true,
      navText: ['<i class="fas fa-chevron-left"></i>', '<i class="fas fa-chevron-right"></i>'],
      responsive: {
        0: {
          items: 1
        },
        768: {
          items: 3
        },
        992: {
          items: 4
        },
        1200: {
          items: 5
        }
      }
    });
}

  window.filterSelection = function(filter) {
    var $owlCarousel = $("#filerOwlCarousel");
    $owlCarousel.owlCarousel('destroy').empty();

    var filteredItems = items.filter('.' + filter);
    $owlCarousel.append(filteredItems);

    initOwlCarousel(filteredItems.length);

    $('.btn').removeClass('active');
    $('button[onclick="filterSelection(\'' + filter + '\', this)"]').addClass('active');
  };

  filterSelection('vitaminas');
  $('button[onclick="filterSelection(\'vitaminas\', this)"]').addClass('active');
});
</script>

```
#### CSS

```html
<style>
  #filerOwlCarousel .item {
    display: flex;
    flex-direction: column;
    padding: 10px 1px !important;
  }

  #filerOwlCarousel .owl-next,
  #filerOwlCarousel .owl-prev {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    display: block !important;
    height: 35px;
    width: 35px;
    background-color: #93d500 !important;
    border-radius: 50% !important;
  }

  #filerOwlCarousel .owl-next {
    right: 0px;
  }

  #filerOwlCarousel .owl-prev {
    left: 0px;
  }

  #filerOwlCarousel .owl-nav i {
    color: white !important;
    font-weight: 900 !important;
  }

  #filerOwlCarousel .card {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    background-color: #fff;
    box-shadow: var(--shadow);
    border-radius: var(--radius);
    overflow: hidden;
    text-align: center;
    padding: 15px;
    min-height: 445px;
  }

  #filerOwlCarousel .card-discount-badge {
    position: absolute;
    top: 10px;
    left: 10px;
    background-color: red;
    color: white;
    padding: 5px 10px;
    border-radius: 5px;
    font-size: 14px;
  }

  #filerOwlCarousel .product-image {
    width: 100%;
    height: 100%;
    object-fit: contain;
    margin: 15px 0;
  }

  #filerOwlCarousel .product-info {
    display: flex;
    flex-direction: column;
    justify-content: center;
    flex-grow: 1;
  }

  #filerOwlCarousel .product-description {
    font-size: 14px;
    font-weight: 600;
    color: #b2b2b2;
    text-align: center;
  }

  #filerOwlCarousel .product-title {
    margin-bottom: 5px;
    font-size: 18px;
    font-weight: 500;
    width: 100%;
    white-space: nowrap;
    text-overflow: ellipsis;
    overflow: hidden;
    color: #595959;
  }

  #filerOwlCarousel .product-price-before {
    font-size: 14px;
    text-decoration: line-through;
    font-weight: 600;
    color: #b2b2b2;
    text-align: center;
  }

  #filerOwlCarousel .product-price-now {
    font-size: 20px;
    font-weight: bold;
    margin-top: auto;
    color: #1788d3;
    text-align: center !important;
  }

  #filerOwlCarousel .btn-add-to-cart {
    background-color: #1788d3 !important;
    color: #fff !important;
    border: none;
    padding: 10px 20px;
    border-radius: var(--radius);
    cursor: pointer;
    text-transform: uppercase;
    font-weight: 600;
    display: block;
    width: 100%;
    margin-top: 10px;
  }

  #filerOwlCarousel .btn-add-to-cart:hover {
    filter: brightness(calc(88 / 100));
  }

  #filerOwlCarousel .btn {
    border: none !important;
    outline: none !important;
    padding: 12px 16px;
    background-color: #f1f1f1;
    cursor: pointer;
    font-family: Montserrat;
    border-radius: var(--radius);
    margin: 5px;
  }

  #myBtnContainer .btn {
    padding: 12px 16px;
    background-color: #f1f1f1;
    cursor: pointer;
    font-family: Montserrat;
    font-weight: 600;
    border-radius: var(--radius);
    margin: 5px;
    box-shadow: var(--shadow);
  }

  #filerOwlCarousel .btn:hover {
    background-color: #ddd;
  }

  #myBtnContainer .btn.active {
    background-color: #1788d3;
    color: white;
    border-radius: var(--radius);
  }

  #myBtnContainer {
    text-align: center;
    margin-bottom: 20px;
  }

  #filerOwlCarousel .labelPromotionsContent {
    margin: 0
  }

  #filerOwlCarousel .apego-spacer {
    width: 100%
  }

  #filerOwlCarousel .badgeDiscount {
    height: 25px;
  }

  #filerOwlCarousel .discont-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    background-color: #e20f18;
    width: 100%;
    height: 100%;
  }

  #filerOwlCarousel .icon-discount {
    width: 15px;
    height: 15px;
  }

  #filerOwlCarousel .discountBg {
    position: relative;
    overflow: hidden;
    padding-left: 8px;
    color: #fff;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    background-color: #ff9094;
    max-height: 25px;
    word-break: break-all;
  }

  #filerOwlCarousel .discountAnimated {
    display: flex;
    align-items: center;
    height: 100%;
  }

  #filerOwlCarousel .discountP {
    display: flex;
    align-items: center;
    height: 100%;
    font-size: .9rem;
  }

  @media (max-width: 768px) {
    #filerOwlCarousel .card {
      width: 90%;
      max-width: 300px;
      margin: auto
    }

    #filerOwlCarousel .product-image {
      height: 150px;
    }

    #filerOwlCarousel .product-info {
      align-items: center;
    }
  }

  @media (min-width: 576px) {
    #filerOwlCarousel .owl-next {
      right: 80px;
    }

    #filerOwlCarousel .owl-prev {
      left: 80px;
    }
  }

  @media (min-width: 768px) {
    #filerOwlCarousel .owl-next {
      right: -10px;
    }

    #filerOwlCarousel .owl-prev {
      left: -10px;
    }
  }

  @media (min-width: 992px) {
    #filerOwlCarousel .owl-next {
      right: -20px;
    }

    #filerOwlCarousel .owl-prev {
      left: -20px;
    }
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
          <h2>Carrusel Card Filtro</h2>
        </div>
      </div>
    </div>
    <div id="myBtnContainer">
      <button class="btn" onclick="filterSelection('vitaminas', this)">Vitaminas</button>
      <button class="btn" onclick="filterSelection('dermo', this)">Dermo</button>
      <button class="btn" onclick="filterSelection('bebes', this)">Bebés</button>
      <button class="btn" onclick="filterSelection('medicamentos', this)">Medicamentos</button>
    </div>
    <!-- Carousel de Productos -->
    <div class="container">
      <div id="filerOwlCarousel" class="owl-carousel owl-theme">
        <!-- Card 1 Vitaminas-->
        <div class="item vitaminas">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+1&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 2 Vitaminas -->
        <div class="item vitaminas">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+2&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 3 Vitaminas -->
        <div class="item vitaminas">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+3&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 4 Vitaminas -->
        <div class="item vitaminas">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+4&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 5 Vitaminas -->
        <div class="item vitaminas">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+5&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 1 Dermo -->
        <div class="item dermo">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+1&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 2 Dermo -->
        <div class="item dermo">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+2&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 3 Dermo -->
        <div class="item dermo">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+3&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 4 Dermo -->
        <div class="item dermo">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+4&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 5 Dermo -->
        <div class="item dermo">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+5&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 1 Bebés -->
        <div class="item bebes">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+1&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 2 Bebés -->
        <div class="item bebes">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+2&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 3 Bebés -->
        <div class="item bebes">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+3&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 4 Bebés -->
        <div class="item bebes">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+4&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 5 Bebés -->
        <div class="item bebes">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+5&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 1 Medicamentos -->
        <div class="item medicamentos">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+1&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 2 Medicamentos -->
        <div class="item medicamentos">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+2&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 3 Medicamentos -->
        <div class="item medicamentos">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+3&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 4 Medicamentos -->
        <div class="item medicamentos">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+4&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
          </div>
        </div>
        <!-- Card 5 Medicamentos -->
        <div class="item medicamentos">
          <div class="card">
            <img src="https://placehold.co/480x480?text=Product+5&font=open+sans" alt="Producto" class="product-image">
            <div class="product-info">
              <h4 class="product-title">Título</h4>
              <p class="product-description">Descripción</p>
              <p class="product-price-now">$ Precio</p>
            </div>
            <a href="#">
              <button class="btn-add-to-cart">Ver más</button>
            </a>
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