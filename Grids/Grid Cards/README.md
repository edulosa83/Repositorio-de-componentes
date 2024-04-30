<a name="inicio"></a>

## Grid Cards

> Considerar que el código necesita Bootstrap pero en el CMS ya están incluidas esas librerías

#### Código JavaScript


#### CSS

```html
<style type="text/css">
  .mainGrid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-gap: 1rem;
    align-items: stretch;
  }

  .cardGrid {
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
  }

  .titulocardGrid h2 {
    font-family: "Montserrat";
    font-size: 25px;
    font-weight: 500;
    color: var(--grey-spf);
  }

  .box-imageBanner a {
    display: block;
    position: relative;
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
    text-decoration: none;
  }

  .box-textCard {
    position: absolute;
    bottom: 0;
    height: auto;
    padding: 0px 0px 0px 20px;
    width: 75%;
  }

  .box-textCard p {
    font-family: "Montserrat";
    font-weight: 600;
    font-size: 20px;
    color: #000;
    background-color: #fff;
    padding: 10px;
    border-radius: 10px;
  }

  .box-textCard p span {
    font-family: "Montserrat";
    font-weight: 300;
    font-size: 14px;
    line-height: 25px;
  }

  .box-textCardMini {
    height: auto;
    padding-top: 10%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .box-textCardMini p {
    font-family: "Montserrat";
    font-weight: 600;
    font-size: 20px;
    color: #000;
  }

  .box-textCardMini p span {
    font-family: "Montserrat";
    font-weight: 300;
    font-size: 14px;
    line-height: 25px;
  }

  .cardGrid img {
    width: 100%;
    object-fit: cover;
    height: auto;
  }

  .cardGrid:nth-child(1) {
    grid-column: span 12;
    grid-row: span 1;
  }

  .cardGrid:nth-child(2),
  .cardGrid:nth-child(3) {
    grid-column: span 6;
    background-color: #fff;
    display: flex;
    flex-direction: column;
  }

  .cardGrid:nth-child(1) .box-imageBanner {
    width: 100%;
    height: 100%;
  }

  .cardGrid:nth-child(1) img {
    width: 100%;
    height: 100% !important;
  }

  .cardGrid:nth-child(2) .box-imageBanner,
  .cardGrid:nth-child(3) .box-imageBanner {
    text-align: center;
    padding: 10px;
    flex-grow: 1;
    margin: 0 auto;
  }

  @media (min-width: 768px) {
    .cardGrid:nth-child(1) {
      grid-column: span 6;
      grid-row: span 1;
    }

    .cardGrid:nth-child(2),
    .cardGrid:nth-child(3) {
      grid-column: span 3;
      background-color: #fff;
      display: flex;
      flex-direction: column;
    }
  }

  @media (min-width: 992px) {
    .box-textCard {
      width: 55%;
    }

    .box-textCard p {
      padding: 10px 20px 10px 10px;
    }
  }

  @media (max-width: 767px) {
    .cardGrid:nth-child(1) img {
      width: 100%;
      height: auto;
      display: block;
    }
  }
</style>

```
#### Código HTML

```html
<div class="landing home">
  <section>
    <div class="wrapper row">
      <div class="col-12 titulocardGrid">
        <div>
          <h2>Título</h2>
        </div>
      </div>
    </div>
    <div class="wrapper row">
      <div class="col-12">
        <div class="mainGrid">
          <div class="cardGrid">
            <div class="box-imageBanner">
              <a href="#" target="_blank">
                <div class="box-textCard">
                  <p>Título 1<br />
                    <span>Subtítulo 1</span>
                  </p>
                </div>
                <img src="https://placehold.co/490x215?text=Banner+1&font=open+sans" alt="Banner 1" id="banner1" />
              </a>
            </div>
          </div>
          <div class="cardGrid">
            <div class="box-imageBanner">
              <a href="#" target="_blank">
                <img src="https://placehold.co/300x135?text=Banner+2&font=open+sans" alt="Banner 2" id="banner2" />
                <div class="box-textCardMini">
                  <p>Título 2<br />
                    <span>Subtítulo 2</span>
                  </p>
                </div>
              </a>
            </div>
          </div>
          <div class="cardGrid">
            <div class="box-imageBanner">
              <a href="#" target="_blank">
                <img src="https://placehold.co/300x135?text=Banner+3&font=open+sans" alt="Banner 3" id="banner3" />
                <div class="box-textCardMini">
                  <p>Título 3<br />
                    <span>Subtítulo 3</span>
                  </p>
                </div>
              </a>
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