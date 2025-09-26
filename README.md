# RFCar
PROJETO1-WEB

## Parte 1: Ideação e protótipo

O segmento de site escolhido para a realização deste projeto é o automotivo  

O site considera algumas necessidades reais de empresas deste segmento, sendo a maior delas, a criação de uma vitrine virtual, consistindo em:
* Home Page com mini vitrine
* Vitrine com filtros
* Landing Page personalizada para cada carro


A ideação foi realizada diretamente no figma:

https://www.figma.com/design/Fk2AKIyseY1ABrGM8TNySN/Projeto---RafaCar?node-id=0-1&t=J6cIamVVcrnE6XEq-0
**Home**
<img width="1059" height="755" alt="ideacao3" src="https://github.com/user-attachments/assets/88a6ab5d-6377-4e41-b600-0c267eac51af" />

**Vitrine**
<img width="1058" height="760" alt="ideacao2" src="https://github.com/user-attachments/assets/d5f22b72-e7df-4918-9d2a-a62e2afea7f1" />

**Veículo**
<img width="1253" height="895" alt="ideacao1" src="https://github.com/user-attachments/assets/d73c062a-bfb1-4bef-b913-48ee0071f5cd" />

## Implementação das páginas com HTML5 e CSS3 + JavaScript

Seguindo a ideação, primeiro, desenvolvemos a página principal

### Página Inicial - Criação de Estrutura Básica HTML
   A parte inicial consistiu na construção da página a bastir de estruturas básicas do html. Optei por dividir a página em 5 blocos, sendo eles:
   1. Header - Se repete em todas as páginas
   2. Banner
   3. Middle
   4. Bottom
   5. Footer - Se repete em todas as páginas

 * Header:<br>
  HTML - O Header foi composto pelo logo da loja, e as opções de acesso do site, além disso, criei uma pasta para armazenar as imagens e manter o projeto organizado:
  <img width="859" height="591" alt="image" src="https://github.com/user-attachments/assets/36fa6cd6-3ab6-4962-8843-0f4c3f3b067a" />

  CSS - Como teremos várias páginas, criei um CSS central para agrupar todos os arquivos que serão utilizados (além de contruir as pastas)
  Além disso, utilizei um reset CSS padrão e incluí uma formatção padrão para todas as páginas
  <img width="504" height="539" alt="image" src="https://github.com/user-attachments/assets/909ca95c-5138-407d-bc84-807521c81722" />

  Para o cabeçalho, o flexbos foi utilizado para alinhar os elementos, o código ficou da seguinte forma:

  `
  
      header {
          background-color: #393F4C;
          color: white;
          list-style: none;
          display: flex;
          align-items: center;
          text-decoration: none;
          padding: 8px;
          font-weight: 700;
          font-size: 16px;
      }
      
      .cabecalho__logo {
          height: 50px;
          width: 50px;
          padding: 8px;
          margin-right: 12px;
      }
      
      .lista_menu {
          display: flex;
          color: white;
          text-decoration: none;
          list-style: none;
      }
      
      .lista_menu_titulo_link {
          text-decoration: none;
          color: white;
          padding: 8px;
      }
  
  Como resultado final, temos:<br>
  <img width="667" height="91" alt="image" src="https://github.com/user-attachments/assets/4227ff57-63dc-40ed-a276-2396749edd95" />
  
  
* Banner:<br> 
  HTML - Para o Banner, uma simples tag de section com uma tag de img foram utilizadas

        <section class="car_banner">
            <img class="car_banner_image" src="/img/banner.jpg  " alt="Imagem BMW Série 2">
        </section>

  CSS - Utilizado para redimensionar e coloar a imagem no lugar correto

        .car_banner {
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: #273C50;
        }
    
        .car_banner_image {
            height: 42vw;
            width: 99.2vw;
        }

* Middle:<br>  
  HTML - No middle, foram criadas classes e apenas um título, criaremos cards com javascript mais adiante,

        <article class="middle">
            <h1 class="middle_title">Principais Modelos</h1>
            <div class="middle_itens" id="card">

        </article>


  CSS - Por hora, somente o titulo foi ajustado, voltaremos neste arquivo para formatar os cardss que serão criados via javascript:

      .middle {
          padding: 12px;
          background-color: var(--fundo-secundario);
      }
      
      .middle_title {
          font-size: 24px;
          font-weight: 700;
          padding: 16px 16px;
          display: flex;
          justify-content: center;    
      }
 

* Bottom:<br>
  HTML - Aqui, os primeiros cards foram criados com imagens no centro e botões. Como neste projeto não teremos interações com todas as páginas imaginadas, apenas o card de "Seminovos" terá o link funcionando.

        <article class="bottom">
            <h2 class="bottom_title">Encontre o seu Carro</h2>
            <div class="bottom_itens">

                <div class="bottom_itens_card">
                    <img class="bottom_itens_card_img" src="/img/0km.png">
                    <h3 class="bottom_itens_card_titulo">Encontre seu 0km</h3>
                    <a class="bottom_itens_card_botao_ancora" href="#">Pesquisar</a>
                </div>

                <div class="bottom_itens_card">
                    <img class="bottom_itens_card_img" src="/img/seminovo.png">
                    <h3 class="bottom_itens_card_titulo">Encontre seu Seminovo</h3>
                    <a class="bottom_itens_card_botao_ancora" href="#">Pesquisar</a>
                </div>

                <div class="bottom_itens_card">
                    <img class="bottom_itens_card_img" src="/img/aluguel.png">
                    <h3 class="bottom_itens_card_titulo">Alugue um Veículo</h3>
                    <a class="bottom_itens_card_botao_ancora" href="#">Pesquisar</a>
                </div>

            </div>
        </article>
  
  CSS - Apesar da imagem atrelada, a formatação de estilo mais "pesada" foi feita pelo próprio CSS
    1.1. - Começamos formatando as cores de fundo e de fonte, bem cmo ajustando os espaço desta seção:

      .bottom {
        background-color: #273C50;
        color: white;
        padding: 12px;
      }

    1.2. - Depois, formatamos os títulos e os itens utilizando flexbox:
      
      .bottom_title {
      font-size: 24px;
      font-weight: 700;
      display: flex;
      justify-content: center;
      }
      
      .bottom_itens {
          display: flex;
          flex-direction: row;
          justify-content: space-around;
          padding: 24px;
      }
      
      .bottom_itens_card {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
      }
   1.3. - A imagem, para caber e ficar centralizada dentro do card

      .bottom_itens_card_img {
        width: 15vw;
        border-radius: 10px;
        margin-bottom: 0.3vw;
      }  
   1.4. - E por último, formatamos o tículo (que vem abaixo do card) e o botão de "Pesquisar":

      .bottom_itens_card_titulo {
          font-size: 18px;
          font-weight: 700;
          margin-bottom: 0.3vw;
      }
      
      .bottom_itens_card_botao_ancora {
        background-color: #D9D9D9;
        color: black;
        margin: 0.5vw;
        padding: 1vw 1vw;
        display: flex;
        justify-content: center;
        text-decoration: none;
        font-size: 18px;
        font-weight: 700;
        border-radius: 10px;
      }

* Footer:
  HTML - O Footer contem apenas as informações do aluno. Se repete em todas as páginas

        <footer class="rodape">
            <p class="rodape_texto">Rafael Queiroz Moraes | 10441847</p>
        </footer>


  CSS - Formatação basica para se adequar ao estido da página, combinando com o cabeçalho

      footer {
          background-color: #393F4C;
          color: white;
          display: flex;
          font-weight: 700;
          justify-content: center;
          align-items: center;
          padding: 8px;
      }


 * JavaScript:<br>
     Nesta página, implementaremos duas funcionalides:
      1. - Criação de Cards a partir de um arquivo json
      2. - Mostrar as parcelas de financiamento quando o ponteiro do mouse passar sobre o botão "Ver parcelas"





* Código completo (sem javascript) - index.html<br>
   Por fim, temos o código completo, com a seção já criada para adicionarmos o javascript

        <body>
            <header>
    
                <a href="index.html"><img class="cabecalho__logo" src="img/logo.svg" alt="Logo"></a>
    
                <article>
                    <ul class="lista_menu">
                        <li class="lista_menu_titulo">
                            <a href="/compra.html" class="lista_menu_titulo_link">Compra</a>
                        </li>
    
                        <li class="lista_menu_titulo">
                            <a href="#" class="lista_menu_titulo_link">Modelos</a>
                        </li>
    
                        <li class="lista_menu_titulo">
                            <a href="#" class="lista_menu_titulo_link">Aluguel</a>
                        </li>
    
                        <li class="lista_menu_titulo">
                            <a href="#" class="lista_menu_titulo_link">Agende seu Test Drive</a>
                        </li>                
                    </ul>
                </article>
            </header>
    
            <section class="car_banner">
                <img class="car_banner_image" src="/img/banner.jpg  " alt="Imagem BMW Série 2">
            </section>
    
            <article class="middle">
                <h1 class="middle_title">Principais Modelos</h1>
                <div class="middle_itens" id="card">
    
            </article>
    
            <article class="bottom">
                <h1 class="bottom_title">Encontre o seu Carro</h1>
                <div class="bottom_itens">
    
                    <div class="bottom_itens_card">
                        <img class="bottom_itens_card_img" src="/img/0km.png">
                        <h3 class="bottom_itens_card_titulo">Encontre seu 0km</h3>
                        <a class="bottom_itens_card_botao_ancora" href="#">Pesquisar</a>
                    </div>
    
                    <div class="bottom_itens_card">
                        <img class="bottom_itens_card_img" src="/img/seminovo.png">
                        <h3 class="bottom_itens_card_titulo">Encontre seu Seminovo</h3>
                        <a class="bottom_itens_card_botao_ancora" href="#">Pesquisar</a>
                    </div>
    
                    <div class="bottom_itens_card">
                        <img class="bottom_itens_card_img" src="/img/aluguel.png">
                        <h3 class="bottom_itens_card_titulo">Alugue um Veículo</h3>
                        <a class="bottom_itens_card_botao_ancora" href="#">Pesquisar</a>
                    </div>
    
                </div>
            </article>
    
            <footer class="rodape">
                <p class="rodape_texto">Rafael Queiroz Moraes | 10441847</p>
            </footer>
    
            <script>
    
            </script>
    
        </body>
   Resultado Final
   <img width="2027" height="1578" alt="image" src="https://github.com/user-attachments/assets/c6c6fd1a-cf51-43c1-b0e5-972ba0a020db" />




### Página de Compra - Criação de Estrutura Básica HTML
   A opagina de compra 4 blocos, sendo eles:
   1. Header - Se repete em todas as páginas - Já demonstrado na construção da página inicial
   2. Filtros
   3. Carros
   4. Footer - Se repete em todas as páginas - Já demonstrado na construção da página inicial

 * Filtros:<br>
  HTML - Os filtros não são responsíos neste projeto, portanto, foram construídos em uma estrutura básica de formulário 
  

  CSS - Como teremos várias páginas, criei um CSS central para agrupar todos os arquivos que serão utilizados (além de contruir as pastas)
  Além disso, utilizei um reset CSS padrão e incluí uma formatção padrão para todas as páginas
  <img width="504" height="539" alt="image" src="https://github.com/user-attachments/assets/909ca95c-5138-407d-bc84-807521c81722" />

  Para o cabeçalho, o flexbos foi utilizado para alinhar os elementos, o código ficou da seguinte forma:

 * Carros:<br>
   Os carros serão criados via Cards no Javascript, portanto, a estrutura é básica:

            <article class="middle_compra">
                <div class="middle_itens_compra" id="card">
            </article>


### Página de Compra - Criação de Estrutura Básica HTML
   A opagina de compra 4 blocos, sendo eles:
   1. Header - Se repete em todas as páginas - Já demonstrado na construção da página inicial
   2. Fotos
   3. Informações sobre o carro
   4. Footer - Se repete em todas as páginas - Já demonstrado na construção da página inicial

Tirando os blocos Header e Footer, os demais serão gerados via javascript, portanto, fica a estrutura simples:

    <body>
        <header>

            <a href="/index.html"><img class="cabecalho__logo" src="/img/logo.svg" alt="Logo"></a>


            <ul class="lista_menu">
                <li class="lista_menu_titulo">
                    <a href="/compra.html" class="lista_menu_titulo_link">Compra</a>
                </li>

                <li class="lista_menu_titulo">
                    <a href="#" class="lista_menu_titulo_link">Modelos</a>
                </li>

                <li class="lista_menu_titulo">
                    <a href="#" class="lista_menu_titulo_link">Aluguel</a>
                </li>

                <li class="lista_menu_titulo">
                    <a href="#" class="lista_menu_titulo_link">Agende seu Test Drive</a>
                </li>                
            </ul>
        </header>

        <section class="imagens" id="card_imagens">

        </section>

        <section class="descricao" id="card_descricao">

        </section>


        <footer class="rodape">
            <p class="rodape_texto">Rafael Queiroz Moraes | 10441847</p>
        </footer>

















