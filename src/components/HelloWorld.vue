<template>
<div class="">
<header class="menu">
    <nav class="navbar sombra">
        <div class="container">
            <div class="logoicon">
                <div class="columns is-8 is-marginless is-mobile">
                    <div class="column logonav">
                        <a href="#"><img src="./imagens/logo.jpg" alt="Logo" style="height: 50px"></a>
                    </div>
                    <div class="column is-narrow iconnav">
                        <ul class="ulicon navbar-burger">
                            <div class="iconnav"><i id="iconphone" class="fas fa-phone"></i></div>
                            <div class="iconnav"><i id="iconwpp" class="fab fa-whatsapp"></i></div>
                            <div class="iconnav"><i class="fas fa-bars"></i></div>
                        </ul>
                    </div>
                </div>    
            </div>
            
            <div class="navbar-menu menusome">
                    <div class="navbar-end mt-4">
                        <ul class="menuul">
                            <li><a href="#"><strong>Início</strong></a></li>
                            <li><a href="https://www.pedoimoveis.com.br/imoveis/a-venda">Comprar</a></li>
                            <li><a href="https://www.pedoimoveis.com.br/imoveis/alugar">Alugar</a></li>
                            <li><div class="navbar-item has-dropdown is-hoverable">
                                    <a class="navbar-link" href="#">Serviços </a>
                                    <div class="navbar-dropdown linhaAmarelab servicos">
                                        <a href="https://www.pedoimoveis.com.br/solicite-seu-imovel" class="navbar-item">Solicite seu Imóvel</a>
                                        <a href="https://www.pedoimoveis.com.br/anuncie-seu-imovel" class="navbar-item">Anuncie seu Imóvel</a>
                                        <a href="https://www.pedoimoveis.com.br/servico/como-negociar-seu-imovel" class="navbar-item">Como negociar seu seu Imóvel</a>
                                        <a href="https://www.pedoimoveis.com.br/servico/minha-lajeado" class="navbar-item">Minha Lajeado</a>
                                        <a href="https://www.pedoimoveis.com.br/servico/aluguel-online" class="navbar-item">Aluguel Online</a>
                                        <a href="https://www.pedoimoveis.com.br/servico/simulacao-de-financiamento" class="navbar-item ">Simulação de Financiamento</a>
                                    </div>
                                </div>
                            </li>
                            <li><a href="https://www.pedoimoveis.com.br/blog">Blog</a></li>
                            <li><a href="https://www.pedoimoveis.com.br/institucional">Institucional</a></li>
                            <li><a href="https://www.pedoimoveis.com.br/contato">Contato</a></li>
                            <li class="navbar-phones-wrapper">
                                <i id="navbaricon" class="fas fa-phone-square navbar-item" style="font-size: 26px; display: flex;">
                                    <div class="modaln mt-5">
                                        <div class="has-background-white modalnav sombra mt-3"> 
                                            <div class="columns is-multiline">
                                                <div class="column is-12 mb-0">
                                                    <strong>Pedó imóveis</strong>
                                                </div>
                                                <div class="column">
                                                    <p class="mb-1">Venda</p>
                                                    <a href="https://api.whatsapp.com/send?phone=+5551983290600"><button class="button is-small btn-nav mb-3">(51) 98329-0600<i class="fab fa-whatsapp"></i></button></a>
                            
                                                    <p class="mb-1">Outros</p>
                                                    <button class="button is-small btn-nav">(51) 3729-8505</button>
                                                </div>
                                                <div class="column">
                                                    <p class="mb-1">Aluguel</p>
                                                    <a href="https://api.whatsapp.com/send?phone=+5551981686400"><button class="button is-small btn-nav">(51) 98168-6400<i class="fab fa-whatsapp"></i></button></a>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </i>
                            </li>
                        </ul>
                    </div>
            </div>         
        </div>
    </nav>
    </header>


    <!--Carrosel-->


    <carousel :per-page="1" :navigate-to="someLocalProperty" :mouse-drag="false" class="carrossel container" v-bind="carouselConfig">
    <slide>
        <a href="https://www.pedoimoveis.com.br/imoveis/a-venda"><img src="./imagens/carousel1.png" alt="Imagem carrossel" class="slide"></a>
    </slide>
    <slide>
        <a href="https://www.pedoimoveis.com.br/servico/como-negociar-seu-imovel"><img src="./imagens/carousel2.png" alt="Imagem carrossel" class="slide"></a>
    </slide>
    <slide>
        <a href="https://conteudo.pedoimoveis.com.br/anuncie-seu-imovel-aqui"><img src="./imagens/carousel3.png" alt="Imagem carrossel" class="slide"></a>
    </slide>
    <slide>
        <a href="https://www.pedoimoveis.com.br/imoveis/alugar"><img src="./imagens/carousel4.png" alt="Imagem carrossel" class="slide"></a>
    </slide>
  </carousel>
    

    <!--Botões-->


    <section class="botoes mt-5">
        <div class="cardh home-search sombra mt-5" >
            <div class="columns">
                <div class="column hideselect " v-if="hideselect">
                    <div class="radio">
                        <input class="radio_input" type="radio" value="option1" name="botaoradio" id="radio1" checked="checked">
                        <label class="radio_label radio_label1" for="radio1">Venda</label>
                        <input class="radio_input" type="radio" value="option2" name="botaoradio" id="radio2">
                        <label class="radio_label radio_label2" for="radio2">Locação</label>
                        <input class="radio_input" type="radio" value="option3" name="botaoradio" id="radio3">
                        <label class="radio_label radio_label3" for="radio3">Lançamentos</label>
                    </div>
                </div>
                <div class="column is-10" id="showColumn" style="display: none; " v-show="aux">
                    <input type="text" class="input_homesearch" name="input-text" id="input-text" placeholder="Código do imóvel">
                </div>
                <div class="column hideselect" v-if="hideselect">
                    <v-select :options="cidades" label="title" placeholder="Cidade" style="padding: 5px;"></v-select>
                </div> 
                <div class="column hideselect " v-if="hideselect">
                    <v-select :options="tipos" label="title" placeholder="Tipo" style="padding: 5px;"></v-select>
                </div>
                <div class="column is-2">
                    <button class="button is-normal botoesbtn is-fullwidth"><strong>Buscar</strong></button>

                </div>
            </div>
        </div>
        <div class="mt-2">
            <a id="btn-code1" v-if="hideselect" v-on:click="ida()">Buscar por código</a>
            <a id="btn-code2" style="display: none;" v-show="aux" v-on:click="volta()">Buscar por localização</a>
        </div>
    </section>


    <!--Lançamentos-->

    <section class="new">
        <div class="container">
            <header class="mt-5">
                <div class="columns is-marginless is-mobile">
                    <div class="column">
                        <h3 class="title linhaAmarela " style="left: 0;">Lançamentos</h3>
                    </div>
                    <div class="column is-narrow">
                        <a href="https://www.pedoimoveis.com.br/lancamentos"><button class="button newbutton is-normal">Ver mais</button></a>
                    </div>
                </div>
            </header>

            <div class="columns is-multiline is-marginless">
                <div class="column is-6">
                    <div class="card boxshadow">
                        <div class="card-image">
                            <a href="https://www.pedoimoveis.com.br/condominio/loteamento-santorini/164805"><img class="new_img" src="./imagens/lancamento.jpeg" alt="Imóvel"></a>
                        </div>
                        <a href="https://www.pedoimoveis.com.br/condominio/loteamento-santorini/164805"><div class="new_imgbg">#</div></a>
                        <div class="new_bgyellow"></div>
                        <div class="new_infotop">
                            <strong>Em construção</strong>
                        </div>
                        <div class="new_info">
                            <strong>Loteamento Santorini</strong>
                            <p>Terreno</p>
                            <p>Conventos</p>
                            <p>Lajeado - RS</p>
                        </div>
                        <a href="https://www.pedoimoveis.com.br/condominio/loteamento-santorini/164805"><div class="new_hr">
                            <hr>
                        </div></a>
                        <div class="new_price">
                            A partir de
                            <p><strong>$ 153.000</strong></p>
                        </div>
                    </div>
                </div>
            </div>    
        </div>
    </section>

        
    <!--Imoveis à Venda-->
    

    <section class="section mt-3 cards">
        <div class="container">
            <header>
                <div class="columns is-marginless is-mobile">
                    <div class="column">
                        <h3 class="title linhaAmarela">Imóveis à Venda</h3>
                    </div>
                
                    <div class="column is-narrow">
                        <a href="https://www.pedoimoveis.com.br/imoveis/a-venda"><button class="button botaocard">Ver mais</button></a>
                    </div>
                </div>
            </header>

            <div class="columns is-multiline is-marginless is-12">
                <div class="column is-3-desktop is-6 --is-flex"> 
                    <div class="card boxshadow">
                        <div class="card-image">
                            <img class="cardimage" src="./imagens/venda1.jpeg" alt="Imóvel">
                        </div>
                        <div class="codimg has-text-weight-bold">
                            932878
                        </div>
                        <div class="bg-casa"></div>
                        <div class="tipoimg has-text-weight-bold">Casa</div>
                        <div class="cimg has-text-weight-bold">
                            RS - Lajeado
                        </div>
                        <div class="card-content">
                            <div class="content">
                                <p class="title is-4">São Cristóvão</p>
                                <p class="subtitle is-6"> Rua Fragrância</p>
                                <p>Linda casa localizada no coração do bairro São Cristóvão! Amplo espaço e conforto são curingas desse...</p>
                            </div>
                            <hr class="my-4">
                            <div class="columns is-marginless is-mobile">
                                <div class="column">
                                    <span class="icon-text">
                                        <span ><h5>2</h5></span>
                                        <span class="icon">
                                            <i class="fas fa-bed"></i>
                                        </span>
                                    </span>
                                </div>
                                <div class="column">
                                    <span class="icon-text">
                                        <span ><h5>1</h5></span>
                                        <span class="icon">
                                        <i class="fas fa-bath"></i>
                                        </span>
                                    </span>
                                </div>
                                <div class="column">
                                    <span class="icon-text">
                                        <span >1</span>
                                        <span class="icon">
                                            <i class="fas fa-car"></i>
                                        </span>
                                    </span>
                                </div>
                            </div>  
                            <hr class="my-4">
                            <div>
                            <h6 class="venda">Venda</h6>
                            <h3 class="numerov"><strong>R$ 525.000</strong></h3>
                            </div>
                        </div>
                    </div>
                </div>
        
                <div class="column is-3-desktop is-6 --is-flex"> 
                    <div class="card boxshadow">
                        <div class="card-image">
                            <img class="cardimage" src="./imagens/venda2.jpeg" alt="Imóvel">
                            <div class="codimg has-text-weight-bold">
                                35262
                            </div>
                            <div class="bg-casa"></div>
                            <div class="tipoimg has-text-weight-bold">Casa</div>
                            <div class="backamarelo"></div>
                            <div class="stipoimg has-text-weight-bold">Semimobiliado</div>
                            <div class="cimg has-text-weight-bold">
                                RS - Lajeado
                            </div>
                        </div>
                        <div class="card-content">
                            <div class="content">
                                <p class="title is-4">Carneiros</p>
                                <p>Condomínio residencial Buena Vista - O requinte de viver bem. Localização: O condomínio é a união...  </p>
                            </div>
                            <hr class="my-4">
                            <div class="columns is-marginless is-mobile">
                                <div class="column">
                                    <span class="icon-text">
                                        <span ><h5>2</h5></span>
                                        <span class="icon">
                                            <i class="fas fa-bed"></i>
                                        </span>
                                    </span>
                                </div>
                                <div class="column">
                                    <span class="icon-text">
                                        <span ><h5>2</h5></span>
                                        <span class="icon">
                                        <i class="fas fa-bath"></i>
                                        </span>
                                    </span>
                                </div>
                                <div class="column">
                                    <span class="icon-text">
                                        <span >1</span>
                                        <span class="icon">
                                            <i class="fas fa-car"></i>
                                        </span>
                                    </span>
                                </div>
                            </div>  
                        <hr class="my-4">
                        <div>
                        <h6 class="venda">Venda</h6>
                        <h4 class="numerov"><strong>R$ 280.000</strong></h4>
                        </div>
                        </div>
                    </div>
                </div>
            
                <div class="column is-3-desktop is-6 --is-flex"> 
                    <div class="card boxshadow">
                        <div class="card-image">
                            <a href="https://www.pedoimoveis.com.br/imovel/apartamento-2-dormitorios-a-venda-sao-cristovao-lajeado/36624"><img class="cardimage" src="./imagens/venda3.jpg" alt="Imóvel"></a>
                        </div>
                        <div class="codimg has-text-weight-bold">
                            356213
                        </div>
                        <div class="backazul"></div>
                        <div class="tipoimg has-text-weight-bold">Apartamento</div>
                        <div class="cimg has-text-weight-bold">
                            RS - Lajeado
                        </div>
                        <div class="card-content">
                            <div class="content">
                                <p class="title is-4">São Cristóvão</p>
                                <p> Lançamento do maior prédio do Rio Grande do Sul São Cristóvão: o imóvel ideal para quem deseja mo...</p>
                            </div>
                        <hr class="my-4">
                        <div class="columns is-marginless is-mobile">
                            <div class="column">
                                <span class="icon-text">
                                    <span ><h5>2</h5></span>
                                    <span class="icon">
                                        <i class="fas fa-bed"></i>
                                    </span>
                                </span>
                                <p class="block">
                                    1 suíte
                                </p>
                            </div>
                            <div class="column">
                                <span class="icon-text">
                                    <span ><h5>2</h5></span>
                                    <span class="icon">
                                    <i class="fas fa-bath"></i>
                                    </span>
                                </span>
                            </div>
                            <div class="column">
                                <span class="icon-text">
                                    <span >1</span>
                                    <span class="icon">
                                        <i class="fas fa-car"></i>
                                    </span>
                                </span>
                            </div>
                        </div>  
                        <hr class="my-4">
                        <div>
                            <h6 class="venda">Venda</h6>
                            <h5 class="numerov"><strong>R$ 260.000</strong></h5>
                        </div>
                        </div>
                    </div>
                </div>
                <div class="column is-3-desktop is-6 --is-flex"> 
                    <div class="card boxshadow">
                        <div class="card-image">
                            <a href="https://www.pedoimoveis.com.br/imovel/apartamento-3-dormitorios-a-venda-americano-lajeado/34534"><img class="cardimage" src="./imagens/venda4.jpg" alt="Imóvel"></a>
                        </div>
                        <div class="codimg has-text-weight-bold">
                            87323
                        </div>
                        <div class="backazul"></div>
                        <div class="tipoimg has-text-weight-bold">Apartamento</div>
                        <div class="cimg has-text-weight-bold ">
                            RS - Lajeado
                        </div>
                        <div class="card-content">
                            <div class="content">
                                <p class="title is-4">Americano</p>
                                <p>Casa de esquina, rua calma e tranquila, bairro nobre, muito agradável e aconchegante.</p>
                            </div>
                            <hr class="my-4">
                            <div class="columns is-marginless is-mobile">
                                <div class="column">
                                    <span class="icon-text">
                                        <span ><h5>2</h5></span>
                                        <span class="icon">
                                            <i class="fas fa-bed"></i>
                                        </span>
                                    </span>
                                </div>
                                <div class="column">
                                    <span class="icon-text">
                                        <span ><h5>1</h5></span>
                                        <span class="icon">
                                        <i class="fas fa-bath"></i>
                                        </span>
                                    </span>
                                </div>
                                <div class="column">
                                    <span class="icon-text">
                                        <span >1</span>
                                        <span class="icon">
                                            <i class="fas fa-car"></i>
                                        </span>
                                    </span>
                                </div>
                            </div>  
                                <hr class="my-4">
                                <div>
                                    <h6 class="venda">Venda</h6>
                                    <h5 class="numerov"><strong>R$ 760.000</strong></h5>
                                </div>
                        </div>
            
                    </div>
                </div>
            </div>
        </div>


    <!--Imoveis para alugar-->

    
    <div class="container mt-3">
        <header>
            <div class="columns is-marginless is-mobile">
                <div class="column">
                    <h2 class="title linhaAmarela">Imóveis para alugar</h2>
                </div>
            
                <div class="column is-narrow">
                    <a href="https://www.pedoimoveis.com.br/imoveis/alugar"><button class="button botaocard">Ver mais</button></a>
                </div>
            </div>
        </header>

        <div class="columns is-multiline is-marginless ">
            <div class="column is-3-desktop is-6 --is-flex"> 
                <div class="card boxshadow">
                    <div class="card-image">
                        <a href="https://www.pedoimoveis.com.br/imovel/sobrado-3-dormitorios-para-alugar-carneiros-lajeado/53808"><img class="cardimage" src="./imagens/alugar1.jpeg" alt="Imóvel"></a>
                    </div>
                    <div class="codimg has-text-weight-bold">
                        32161
                    </div>
                    <div class="bg-casa"></div>
                    <div class="tipoimg has-text-weight-bold">Casa</div>
                    <div class="cimg has-text-weight-bold">
                        RS - Lajeado
                    </div>
                    <div class="card-content">
                        <div class="content">
                            <p class="title is-4">Carneiros</p>
                            <p class="subtitle is-6"> Rua dos Jasmins</p>
                            <p>Lindo sobrado semi mobiliado localizado no bairro Carneiros em Lajeado. O sobrado que dispõe de: - 3...</p>
                        </div>
                        <hr class="my-4">
                        <div class="columns is-marginless is-mobile">
                            <div class="column">
                                <span class="icon-text">
                                    <span ><h5>2</h5></span>
                                    <span class="icon">
                                        <i class="fas fa-bed"></i>
                                    </span>
                                </span>
                            </div>
                            <div class="column">
                                <span class="icon-text">
                                    <span ><h5>1</h5></span>
                                    <span class="icon">
                                    <i class="fas fa-bath"></i>
                                    </span>
                                </span>
                            </div>
                            <div class="column">
                                <span class="icon-text">
                                    <span >1</span>
                                    <span class="icon">
                                        <i class="fas fa-car"></i>
                                    </span>
                                </span>
                            </div>
                        </div>  
                        <hr class="my-4">
                        <div>
                            <h6 class="venda">Locação</h6>
                            <h5 class="numerov"><strong>R$ 855</strong></h5>
                        </div>
                    </div>
                </div>
            </div>
    
            <div class="column is-3-desktop is-6 --is-flex"> 
                <div class="card boxshadow">
                    <div class="card-image">
                        <a href="https://www.pedoimoveis.com.br/imovel/sobrado-3-dormitorios-para-alugar-carneiros-lajeado/53808"><img class="cardimage" src="./imagens/alugar2.jpeg" alt="Imóvel"></a>
                    </div>
                    <div class="codimg has-text-weight-bold">
                        425632
                    </div>
                    <div class="bg-casa"></div>
                    <div class="tipoimg has-text-weight-bold">Casa</div>
                    <div class="cimg has-text-weight-bold">
                        RS - Lajeado
                    </div>
                    <div class="card-content">
                        <div class="content">
                            <p class="title is-4">Hidráulica</p>
                            <p>Eu te entendo, morar em casa é uma delícia..... Esta casa foi inteiramente reformada há alguns ano...</p>
                        </div>
                        <hr class="my-4">
                        <div class="columns is-marginless is-mobile">
                            <div class="column">
                                <span class="icon-text">
                                    <span ><h5>3</h5></span>
                                    <span class="icon">
                                        <i class="fas fa-bed"></i>
                                    </span>
                                    <p class="block">
                                        2 suíte
                                    </p>
                                </span>
                            </div>
                            <div class="column">
                                <span class="icon-text">
                                    <span ><h5>5</h5></span>
                                    <span class="icon">
                                    <i class="fas fa-bath"></i>
                                    </span>
                                </span>
                            </div>
                            <div class="column">
                                <span class="icon-text">
                                    <span >2</span>
                                    <span class="icon">
                                        <i class="fas fa-car"></i>
                                    </span>
                                </span>
                            </div>
                        </div>  
                        <hr class="my-4">
                        <div>
                            <h6 class="venda">Locação</h6>
                            <h5 class="numerov"><strong>R$ 4.200</strong></h5>
                        </div>
                    </div>
                </div>
            </div>
        
            <div class="column is-3-desktop is-6 --is-flex"> 
                <div class="card boxshadow">
                    <div class="card-image">
                        <img class="cardimage" src="./imagens/alugar3.jpeg" alt="Imóvel">
                    </div>
                    <div class="codimg has-text-weight-bold">
                        43525
                    </div>
                    <div class="backazul"></div>
                    <div class="tipoimg has-text-weight-bold">Apartamento</div>
                    <div class="backamarelo"></div>
                    <div class="stipoimg has-text-weight-bold">Semimobiliado</div>
                    <div class="cimg has-text-weight-bold">
                        RS - Lajeado
                    </div>
                    <div class="card-content">
                        <div class="content">
                            <p class="title is-4">Olarias</p>
                            <p> - Cobertura exclusiva, horizontal e plana; - Opção de 4 boxes de garagem; -totalmente automatizad...</p>
                        </div>
                    <hr class="my-4">
                    <div class="columns is-marginless is-mobile">
                        <div class="column">
                            <span class="icon-text">
                                <span ><h5>2</h5></span>
                                <span class="icon">
                                    <i class="fas fa-bed"></i>
                                </span>
                            </span>
                        </div>
                        <div class="column">
                            <span class="icon-text">
                                <span ><h5>2</h5></span>
                                <span class="icon">
                                <i class="fas fa-bath"></i>
                                </span>
                            </span>
                        </div>
                        <div class="column">
                            <span class="icon-text">
                                <span >1</span>
                                <span class="icon">
                                    <i class="fas fa-car"></i>
                                </span>
                            </span>
                        </div>
                    </div>  
                    <hr class="my-4">
                    <div>
                        <h6 class="venda">Locação</h6>
                        <h5 class="numerov"><strong>R$ 3.500</strong></h5>
                    </div>
                    </div>
                </div>
            </div>
            <div class="column is-3-desktop is-6 --is-flex"> 
                <div class="card boxshadow">
                    <div class="card-image">
                        <a href="https://www.pedoimoveis.com.br/imovel/sala-comercial-para-alugar-centro-lajeado/58325"><img class="cardimage" src="./imagens/alugar4.jpeg" alt="Imóvel"></a>
                    </div>
                    <div class="codimg has-text-weight-bold">
                        65382
                    </div>
                    <div class="backazul"></div>
                    <div class="tipoimg has-text-weight-bold">Sala Comercial</div>
                    <div class="cimg has-text-weight-bold">
                        RS - Lajeado
                    </div>
                    <div class="card-content">
                        <div class="content">
                            <p class="title is-4">Centro</p>
                            <p>Excelente sala comercial de aproximadamente 40 m², com ótima localização no centro de Lajeado. Sala...</p>
                        </div>
                        <hr class="my-4">
                        <div class="columns is-marginless is-mobile">
                            <div class="column">
                                <span class="icon-text" style="display: flex; align-items: center; justify-content: center;">
                                    <span ><h5>1</h5></span>
                                    <span class="icon">
                                    <i class="fas fa-bath"></i>
                                    </span>
                                </span>
                            </div>
                        </div>  
                        <hr class="my-4">
                        <div>
                            <h6 class="venda">Locação</h6>
                            <h5 class="numerov"><strong>R$ 1.000</strong></h5>
                        </div>
                    </div>
                </div>
            </div>
        </div>


    <!--Posts em destaque-->


        <div class="container mb-0 mt-3 post"> 
            <header class="mt-5 mb-1">
                <h2 class="title linhaAmarela">Posts em destaque</h2>
            </header>

            <div class="columns is-marginless">
                <div class="column is-6 --is-flex "> 
                    <div class="card boxshadow" >
                        <div class="card-image">
                            <figure class="image is-3by2"><a href="https://www.pedoimoveis.com.br/blog/2021/2/8/como-escolher-a-sala-ideal-para-o-seu-negocio-2299"><img class="cardimage" src="./imagens/post1.jpg" alt="Imóvel"></a></figure>
                        </div>
                        <div class="card-content">
                            <div class="content">
                                <p class="title is-4 link-post"><a href="https://www.pedoimoveis.com.br/blog/2021/2/8/como-escolher-a-sala-ideal-para-o-seu-negocio-2299">COMO ESCOLHER A SALA IDEAL PARA O SEU NEGÓCIO?</a></p>
                                <h5 class="mb-0"><p>Olá, Tudo bem com você? Hoje, vamos conversar com os nossos clientes que tem o espírito empreendedor, isso mesmo, para aqueles que respiram negócio, que já tem o seu ou que querem abrir nesse ano....</p></h5>
                                <p>Há 5 meses...</p>
                            </div>
                        </div>
                    </div>
                </div>
            
                <div class="column is-6 --is-flex"> 
                    <div class="card boxshadow " >
                        <div class="card-image">
                            <figure class="image is-3by2"><a href="https://www.pedoimoveis.com.br/blog/2020/11/23/o-que-e-casa-verde-e-amarela-2174"><img class="cardimage" src="./imagens/post2.png" alt="Post"></a></figure>
                        </div>
                        <div class="card-content">
                            <div class="content">
                                <p class="title is-4 link-post"><a href="https://www.pedoimoveis.com.br/blog/2020/11/23/o-que-e-casa-verde-e-amarela-2174">O que é Casa Verde e Amarela?</a></p>
                                <h5 class="mb-0"><p>Você deve ter escutado “Casa verde e amarela” nas últimas semanas e provavelmente deve ter dúvidas sobre o assunto. Então, nesse post do blog vamos esclarecer um pouco o assunto, mas frisamos que...</p></h5>
                                <p>Há 11 meses...</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    </section>


    <!--Rodapé-->


    <section class="rodape">
    <div class="container">
        <div class="columns">
            <div class="column ">
                <div>
                    <span class="icon-text">
                        <span class="icon">
                            <i class="fas fa-map-marker-alt" style="position: absolute; left: -15px;"></i>
                        </span>
                        <span ><h4 class="" style="position: absolute; left: 0px; font-size: 1.2em; font-weight: 700; color: #6b6b6b;">Pedó Imóveis</h4></span>
                    </span>
                </div>
                <div class="mt-4 black">
                    <h5 class="has-text-weight-bold" style="color: #1d1d1d;">Endereço</h5>
                    <p class="">Lajeado-RS</p>
                    <p>Av Benjamin Constant, 1737, Florestal</p>
                    <p>Loja 01</p>
                    <p>95900-700</p>
                </div>

                <div class="mt-4">
                    <h5 class="has-text-weight-bold">Horário de Atendimento</h5>
                    <p>Segunda a quinta-feira: 8:00 às 18:30 | Sexta-feira: 8:00 às 18:00 | Sábado: 8:30 às 12:00</p>
                </div>
                <div class="mt-4 telefones">
                    <h5 class="has-text-weight-bold">Telefones</h5>
                    <p class="has-text-weight-light">Venda</p>
                    <a href="https://api.whatsapp.com/send?phone=+5551983290600">(51) 98329-0600 <i class="fab fa-whatsapp"></i></a>
                    <p class="has-text-weight-light">Aluguel</p>
                    <a href="https://api.whatsapp.com/send?phone=+5551981686400">(51) 98168-6400 <i class="fab fa-whatsapp"></i></a>
                    <p class="has-text-weight-light">Outros</p>
                    <a href="#">(51) 3729-8505</a>
                </div>
            </div>
        </div>
    </div>
        <div class="bordat mt-4 mb-5">
            <div class="container">
                <div class="columns is-desktop mt-4 rodape2">
                    <div class="column is-3 ">
                        <figure class="image is-3by1" ><a href="#"><img src="./imagens/logo.jpg" class = "imgrodape" alt="Logo"></a></figure>
                        <p class="rodape2 has-text-weight-light has-text-centered">CRECI 23.935-J</p>
                    </div>
                    <div class="column is-2 some rodape-link">
                        <a href="#"><strong>Início</strong></a>
                        <a href="https://www.pedoimoveis.com.br/imoveis/a-venda"><p>Comprar</p></a>
                        <a href="https://www.pedoimoveis.com.br/imoveis/alugar"><p>Alugar</p></a>
                        <a href="https://www.pedoimoveis.com.br/lancamentos"><p>Lançamentos</p></a>
                    </div>
                    <div class="column is-2 some rodape-link">
                        <a href="https://www.pedoimoveis.com.br/institucional"><p>Institucional</p></a>
                        <a href="https://www.pedoimoveis.com.br/blog"><p>Blog</p></a>
                        <a href="https://www.pedoimoveis.com.br/trabalhe-conosco"><p>Trabalhe conosco</p></a>
                        <a href="https://www.pedoimoveis.com.br/contato"><p>Contato</p></a>
                    </div>
                    <div class="column is-2 rodape2 rodape-link">
                        <a href="https://www.pedoimoveis.com.br/termos-de-uso"><p>Termos de Uso</p></a>
                        <a class="poli" href="https://www.pedoimoveis.com.br/politica-de-privacidade"><p>Política de Privacidade</p></a>
                    </div>
                    <div class="column iconrodape is-2" style="margin-left: 0;">
                        <span class="icon" style="margin-right:6px;">
                            <a href="https://www.facebook.com/pedoimoveislajeado"><i class="fab fa-facebook-square"></i></a>
                        </span>
                        <span class="icon" style="margin-right:6px;">
                            <a href="https://www.instagram.com/pedoimoveis/"><i class="fab fa-instagram"></i></a>
                        </span>
                        <span class="icon">
                            <a href="https://www.youtube.com/channel/UC2v-zB4A8t8isP2yOZEYMZg"><i class="fab fa-youtube-square"></i></a>
                        </span>
                    </div>
                </div>
            </div>
        </div>    

        <div class="bordat mt-5">
            <div class="has-text-centered mt-5">
                <a href="https://www.jetimob.com/?utm_term%3Dhttps%3A%2F%2Fwww_pedoimoveis_com_br%2F%26utm_source%3Dfooter-bar%26utm_medium%3Dskyler%26utm_campaign%3Dsite">
                    <img src="./imagens/jetimob.png" style= "object-fit: cover;" alt="Logo Jetimob">
                </a>
            </div>
        </div>
        
    </section>

    <div id="widget" class="widget" v-on:click="show()">
        <div class="widget-content">
            <img src="https://assets.suiteshare.com/whts/widget_logo.svg" alt="Atendimento"><strong>Whatsapp</strong>
        </div>
    </div>

    <div class="wid" v-if="widshow">
        <div class="has-background-white wid-content sombra"> 
                <div class="btn-close">
                    <button class="modal-close is-large" aria-label="close" v-on:click="unshow()"><i class="fas fa-times"></i></button>
                </div>
                <div class="bgwid">
                    <div class="bgwid-content">
                        <img src="./imagens/logo.png" style="object-fit:contain; height: 80px; width: 80px;">
                        <p class="title mb-1">Olá</p>
                        <p class="mb-4" style="padding-bottom: 14px;">Por favor, escolha o setor que deseja atendimento.</p>
                    </div>
                </div>
                <div class="columns widbtn" style="padding: 20px;">
                    <div class="column">
                        <div class="card mb-4">
                            <div class="media">
                                <div class="media-left">
                                    <figure class="image is-48x48">
                                    <img class="is-rounded" src="https://assets.suiteshare.com/forks/5eda4a379b9ab/logo%202.png" alt="Placeholder image">
                                    </figure>
                                </div>
                                <div class="media-content">
                                    <p class="title is-6">Aluguel Pedó Imóveis</p>
                                    <p class="subtitle is-6">online</p>
                                </div>
                            </div>
                            <div class="content contnt-card-wid">
                                <a href="https://whts.co/cap_aluguel" style="display: flex; width: 100%;"><button class="button btn-widget"><i class="fab fa-whatsapp"></i> Whatsapp</button></a>
                            </div>
                        </div>
                        <div class="card">
                            <div class="media">
                                <div class="media-left">
                                    <figure class="image is-48x48">
                                    <img class="is-rounded" src="https://assets.suiteshare.com/forks/5eda4a379b9ab/logo%202.png" alt="Placeholder image">
                                    </figure>
                                </div>
                                <div class="media-content">
                                    <p class="title is-6">Vendas Pedó Imóveis</p>
                                    <p class="subtitle is-6">online</p>
                                </div>
                            </div>
                            <div class="content contnt-card-wid">
                                <a href="https://whts.co/vendas_pedo" style="display: flex; width: 100%;"><button class="button btn-widget"><i class="fab fa-whatsapp"></i> Whatsapp</button></a>
                            </div>
                        </div>
                    </div>
                </div> 
        </div>
    </div>

    <div class="modal" v-if="modal">
        <div class="modal-background"></div>
        <div class="modal-content has-background-white modalt"> 
            <h5 class="title mb-2">Pedó Imóveis</h5>
            <button class="button"><strong>(51) 3729-8505</strong></button>
            <h6 class="has-text-light-bold">Venda</h6>
            <button class="button"><strong>(51) 98329-0600</strong><i class="fab fa-whatsapp"></i></button>
            <h6 class="has-text-light-bold">Aluguel</h6>
            <button class="button"><strong>(51) 98168-6400</strong><i class="fab fa-whatsapp"></i></button>
        </div>
    </div>

    <div class="modal modalwpp">
        <div class="modal-background modalbg"></div>
        <div class="modal-content has-background-white modalw"> 
            <h5 class="title mb-2">Pedó Imóveis</h5>
            <h6 class="has-text-light-bold">Venda</h6>
            <button class="button is-fullwidth"><strong>(51) 98329-0600</strong><i class="fab fa-whatsapp"></i></button>
            <h6 class="has-text-light-bold">Aluguel</h6>
            <button class="button is-fullwidth"><strong>(51) 98168-6400</strong><i class="fab fa-whatsapp"></i></button>
        </div>
    </div>

    </div>
</template>

<script>
import * as Carousel from 'vue-carousel';
import Vue from 'vue';
import vSelect from 'vue-select';

Vue.component("v-select", vSelect);

export default {
    name: "Pag",
    
    components: {
        Carousel: Carousel.Carousel,
        Slide: Carousel.Slide,
    },
  

  data(){ 
      return{
          carouselConfig:{ 
              perPage: 1,
              autoplay: true,
              autoplayTimeout: 7000,
              loop: true,
              navigationEnabled: true,
          },
      
      hideselect: true,
      aux: false,   
      widshow: false,
      modal: false,

                       
      cidades: [
        { title: "Arroio do Meio - RS" },
        { title: "Capão da Canoa - RS" },
        { title: "Cruzeiro do Sul - RS" },
        { title: "Estrela - RS" },
        { title: "Fazenda Vilanova - RS" },
        { title: "Lajeado - RS" },
        { title: "Marques de Souza - RS" },
        { title: "Santa Clara do Sul - RS" }


      ],
                 
      tipos: [
        { title: "Box" },
        { title: "Casa" },
        { title: "Casa Comercial" },
        { title: "Casa de Condomínio" },
        { title: "Chácara" },
        { title: "Cobertura" },
        { title: "Duplex" },
        { title: "Geminado" },
        { title: "Kitnet" },
        { title: "Loft" },
        { title: "Loja" },
        { title: "Pavilhão" },
        { title: "Ponto Comercial" },
        { title: "Sala Comercial" },
        { title: "Sobrado" },
        { title: "Terreno" },
        { title: "Terreno Comercial" },
        { title: "Área Rural" },
        { title: "Prédio Residencial" }
      ], 


    }
    },

    methods:{
        ida(){
            this.hideselect = false,
            this.aux = true

        },
        
        volta(){
            this.hideselect = true,
            this.aux = false

        },

        show(){
            this.widshow = true
        },

        unshow(){
            this.widshow = false
        },

    }

    
}
</script>

<style>

/* Geral */

body{
    font-family: 'Montserrat', sans-serif;
}

.boxshadow{
    box-shadow: 0 0 8px 0 #00000036;
    transition: all ease-in-out .2s;
}

.sombra{
    box-shadow: 0 0 8px 0 #00000036;
}

.block{
    font-size: 11px;
}

@media (max-width:1022px){
    .menusome{
        display: none;
    }

    .ulicon{    
        display: flex!important;;
        flex-flow: row;
        justify-content: space-around;
        align-items: center;
        padding: 16px;
        margin-left: 16px;
        font-size: 25px;
    }

}

@media (max-width:380px){
    .radio{
        display: grid!important;;
    }

    .radio_label2{
        border-left: solid 1px #08145e!important;;
        border-right: solid 1px #08145e!important;;
        border-radius: 4px;
    }

    .radio_label{
        border-radius: 4px!important;;
    }

    .radio_label3{
        border-radius: 4px!important;;
    }
}

@media (max-width:425px){
    .modalwid{
        left: 0!important;;
    }
}


@media (max-width:1024px){
    .rodape2{
        display: flex;
        flex-flow: column;
        align-items: center;
        justify-content: center;
    }
    .some{
        display: none;
    }
    .iconrodape{
        font-size: 25px;
        display: flex;
        flex-flow: row;
        justify-content: space-evenly;
    }
    .poli{
        display: flex;
        flex-flow: column;
        align-items: center;
        justify-content: center;
        padding: 4px;
        font-size: 15px;
        width: max-content;
    }

}

@media (max-width:770px){
    .carrossel{
        display: none;
    }
}

@media (max-width:382px){
    .radio{
        display: grid!important;
    }

    .radio_label2{
        border-left: solid 1px #08145e!important;
        border-right: solid 1px #08145e!important;
    }

}

.title{
    font-size: 1.85rem;
}


/* Menu */


.menu{
    background-color: #fffffff7;
    position: sticky;
    width: 100%;
    top: 0;
    z-index: 1000;
    border-top: 4px solid #ffcc00;
}

.menu a{
    color: black;
    text-decoration: none;
    padding: 16px;
    text-align: right;
}

.menu a:hover{
    color: #0F218A;
}

.menuul{
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    padding: 16px;
    margin-bottom: 5px;
    padding-top: 5px;
}

.logonav{
    display: flex;
}

.ulicon{
    display: none;
}

.iconnav{
    margin-right: 12px;
}

.linhaAmarelab{
    border-bottom: 4px solid #ffcc00;
}

.modaln{
    font-family: 'Montserrat', sans-serif;
    font-size: initial;
    font-weight: initial;
}

.modaln a{
    padding: 0;
}

.navbar-phones-wrapper .modaln {
    transform: scale(0);
    transition: all .2s ease-in-out;
    transition-delay: .3s;
    transform-origin: top right;
}

.btn-nav:hover{
    text-decoration: underline;
    color: #0F218A;
    border: solid 1px #0F218A;
}

.navbar-phones-wrapper:hover .modaln {
    transform: scale(1);
}

.servicos{
    background-color: #e0e0e0;
}

.navbar-item:hover{
    background-color: transparent;
}

.navbar-burger:hover{
    background-color: transparent!important;;
}

.navbar-burger{
    cursor: initial;
}


/* Carrossel */

.carrossel{
    widows: 100%;
    margin-top: 15px;
}

.VueCarousel-pagination{
    display: none;
}

.slide{
    border-radius: 6px;
}

.VueCarousel-inner{
    height: auto;
}

.VueCarousel-navigation-prev[data-v-453ad8cd]{
    position: absolute;
    left: 25px;
    top: 50%;
    color: white;
}

.VueCarousel-navigation-next[data-v-453ad8cd]{
    position: absolute;
    right: 25px;
    top: 50%;
    color:white;
}

/* Botões */


.home-search{
    max-width:min(95vw, 1300px); 
    width: 100%;
    padding: 20px;
    border-radius: 5px;

}

.input_homesearch{
    width: 100%;
    padding: 11px;
}

.botoes{
    z-index: -1;
    display:flex; 
    flex-flow:column; 
    align-items: center;
}

.telefones a{
    color: #0F218A;
}

.telefones a:hover{
    color: #0F218A;
}


.botoesbtn{
    background-color: rgba(15,33,138,0.9);
    color: white;
}

.botoesbtn:hover{
    background-color: #0f249e;
    color: white;
}

.botoes a{
    color: #0F218A;
}

.botaocard{
    background-color: #e0e0e0;
    border: 1px solid #0F218A;
    color: #0F218A;
}

.botaocard:hover{
    background-color: rgba(15,33,138,0.9);
    color: white;
}


.radio{
    display: inline-flex;
    border-radius: 7px;
    width: 100%;
}

.radio_label{
    padding: 10px 15px;
    font-size: 16px;
    color: #0F218A;
    background-color: white;
    border: 1px solid #0F218A;
    cursor: pointer;
    border-radius: 7px;
}

.radio_label:hover{
    background-color: rgba(15,33,138,0.9);
    color: white;
}

.radio_input{
    display: none;
}

.radio_input:checked + .radio_label{
    background-color: rgba(15,33,138,0.9);
    color: white;
}

.radio_label1{ 
    text-align: center;
    border-radius: 4px 0px 0px 4px;
    width: 50%;
    border-right: solid 1px #08145e;
}

.radio_label2{
    text-align: center;
    width: 50%;
    border-radius: 0px;
    border-left: none;
    border-right: none;
}

.radio_label3{
    text-align: center;
    border-radius: 0px 4px 4px 0px;
    width: 50%;
    border-left: solid 1px #08145e;
}

.button.is-small:not(.is-rounded) {
    border-radius: 8px;
}



/* Lançamentos */

.new .title{
    font-weight: initial;
}

.newbutton{
    background-color: white;
    border: 1px solid #0F218A;
    color: #0F218A;
}

.newbutton:hover{
    background-color: rgba(15,33,138,0.9);
    color: white;
}

.new_imgbg{
    position: absolute;
    color: transparent;
    background-image: linear-gradient(transparent, black);
    bottom: 0;
    width: 100%;
    height: 69%;
}

.new_img{
    object-fit: contain;
    width: 100%;
    height: 100%;
}

.new_hr {
    position: absolute;
    bottom: 0;
    width: 93%;
    left: 16px;
}

.new_hr hr{
    background-color: white;
}

.info_new{
    background-image: linear-gradient(transparent, black);
}

.new_info strong{
    color: white;
}

.new_info{
    position: absolute;
    color: white;
    bottom: 64px;
    left: 16px;
    text-shadow: black 0.1em 0.1em 0.2em;
}

.new_bgyellow{
    position: absolute;
    top: 28px;
    width: 151px;
    height: 39px;
    background-color: #ffcc00;
    border-radius: 0px 7px 7px 0px;
}
.new_infotop strong{
    color:white;
}

.new_infotop{
    position: absolute;
    top: 35px;
    left: 15px;
    color: white;
}

.new_price{
    position: absolute;
    right: 2%;
    bottom: 40%;
    color: white;
    text-shadow: black 0.1em 0.1em 0.2em;

}

.new_price strong{
    color: white;
    font-size: 23px;

}

/* Cards */

.cards .title{
    font-weight: initial;
}

.--is-flex {
    display: flex;
}

.cardimage{
    height: 225px;
    width: 100%;
    object-fit: cover;
}

hr{
    height:1px;
    border-width:0;
    color:gray;
    background-color:gray;
}

.boxshadow:hover{
    transform: scale(1.02);
}

.linhaAmarela{
    border-bottom: 4px solid #ffCC00;
    display: inline-block;
}

.column a{
    text-decoration: none;
    color: black;
}

.column a:hover{
    color:blue
}

.section{
    background-color:#e0e0e0
}

.stipoimg{
    position: absolute;
    top: 49px;
    left: 7px;
    color: white;
    text-shadow: black 0.1em 0.1em 0.2em
    
}

.backamarelo{
    position: absolute;
    top: 49px;
    left: 0px;
    background-color: #ffCC00;
    border-radius: 0px 6px 6px 0px; 
    width: 139px;
    height: 24px;
}

.cimg{
    position: absolute;
    top: 194px;
    left: 6px;
    color: white;
    text-shadow: black 0.1em 0.1em 0.2em
}

.codimg{
    position: absolute;
    top: 8px;
    right: 6px;
    color: white;
    text-shadow: black 0.1em 0.1em 0.2em
}

.link-post a{
    color: rgba(15,33,138,0.9);
}

.link-post a:hover{
    color: rgba(15,33,138,0.9);
    text-decoration: underline;
}

.post .title{
    font-weight: initial;
}


.tipoimg{
    position: absolute;
    top: 20px;
    left: 7px;
    color: white;
}

.backazul{
    position: absolute;
    top: 20px;
    left: 0px;
    background-color: #0F218A;
    border-radius: 0px 6px 6px 0px;    
    width: 130px;
    height: 24px;
}

.bg-casa{
    position: absolute;
    top: 20px;
    left: 0px;
    background-color: #0F218A;
    border-radius: 0px 6px 6px 0px;    
    width: 53px;
    height: 24px;
}

.numerov{
    font-size: 22px;
}

.venda{
    color: gray;
    font-size: 15px;
}

/* Rodapé */

.bordat{
    border-top: 1px solid #d3d3d3;
}

.rodape{
    color: black;
    padding: 16px;
    border-top: 4px solid #ffcc00;
    padding-top: 20px;
    padding-bottom: 20px;
}

.iconrodape{
    margin-left: 16px;
    font-size: 25px;
}

.iconrodape a{
    color: #0F218A;
}

.iconrodape a:hover{
    color: #ffcc00;
}

.imgrodape{
    object-fit: contain;
}

.telefones a{
    color: #0F218A;
}

.telefones a:hover{
    color: #0F218A;
    text-decoration: underline;
}

.rodape-link a:hover{
    color: #0F218A;    
}

/* Modal */


.modal button{
    background-color: #0F218A;
    color: white;
}

.modalt{
    width: auto;
    padding: 21px;
    border-radius: 7px 7px 7px 7px;
}

.modalw{
    width: 309px;
    padding: 21px;
    border-radius: 7px 7px 7px 7px;
}

.modal-close{
    position: absolute;
}

.bgwid{
    background: url(https://assets.suiteshare.com/whts/img/temas/0.png) 0px 0px / 80% repeat, linear-gradient(
135deg, rgb(25, 67, 127) 0%, rgba(25, 67, 127, 0.8) 100%);;
    color: white;
}

.bgwid .title{
    color: white;
}

.bgwid-content{
    padding: 20px;
}

.modalwid .card{
    padding: 20px;
    position: relative;
    bottom: 51px;
}
.widget img{
    object-fit: cover;
    height: 24px;
    margin-right: 8px;
}

.widget-content{
    display: flex;
}

.modalwid{
    width: 374px;
    border-radius: 11px;
    position: absolute;
    left: 20px;
    bottom: 94px;
    
}

.widbtn button{
    background-color: #00bc5d;
    color: white;
}

.modalwid .modalclose{
    background-color: lightslategray;
    color: white;
}


.contnt-card-wid{
    display: flex;
    flex-flow: row;
    justify-content: center;
}

.btn-widget{
    width: 100%;
    border-radius: 24px;
    padding: 22px;
    margin: 10px;
    
}

.btn-widget:hover{
    background-color: #00bc5d;
    color: white;
}

.btn-close button{
    background-color: rgba(10,10,10,.3);
}

.widget{
    background-color: #00bc5d;
    max-width: 460px;
    border-radius: 60px;
    cursor: pointer;
    position: fixed;
    bottom: 20px;
    left: 20px;
    padding: 20px;
    color: white;
}

.widget strong{
    color: white;
}

.modalnav{
    position: absolute;
    top: 11%;
    right: 11%;
    padding: 30px;
    border-radius: 8px;
    width: 400px;
}

.modalnav button{
    border: 1px solid #0F218A;
    color: #0F218A;
    background-color: white;
}

.modalwidget .modal-background{
    background-color: transparent;
}

/* Pop-up */

.pop-up{
    background-color: white;
    width: 290px;
    border-radius: 12px;
    position: fixed;
    bottom: 100px;
    left: 20px;
    opacity: 1;
    color: white;
    transition: all 0.3s ease-out;
}

.pop-content{
    margin: 0px!important;
    margin-top: 11px!important;
    margin-bottom: 8px!important;
    padding: 16px 22px 16px 22px;
}

.pop-info{
    font-size: 13px;
    line-height: 18px;
    color: #646B72;
    font-family: 'roboto','arial',sans-serif;
    font-weight: 400;
}

.pop-close{
    position: relative;
    
}

.btn-pop{
    background-color: rgba(10,10,10,.3);
    right: 0;
    top: -45px;
}

/* Widget */

.wid-content{
    width: 374px;
    border-radius: 6px;
    position: fixed;
    left: 20px;
    bottom: 94px;
    
}

.wid-content .card{
    padding: 20px;
    position: relative;
    bottom: 51px;
}

.wid-content .modalclose{
    background-color: lightslategray;
    color: white;
}


.bgwid{
    background: url(https://assets.suiteshare.com/whts/img/temas/0.png) 0px 0px / 80% repeat, linear-gradient(
135deg, rgb(25, 67, 127) 0%, rgba(25, 67, 127, 0.8) 100%);;
    color: white;
    border-radius: 6px 6px 0px 0px;
}

.widget img{
    object-fit: cover;
    height: 24px;
    margin-right: 8px;
}

.contnt-card-wid{
    display: flex;
    flex-flow: row;
    justify-content: center;
}

.btn-widget{
    width: 100%;
    border-radius: 24px;
    padding: 22px;
    margin: 10px;
    
}

.btn-widget:hover{
    background-color: #00bc5d;
    color: white;
}

.btn-close button{
    background-color: rgba(10,10,10,.3);
}

.bgwid .title{
    color: white;
}

.bgwid-content{
    padding: 20px;
}

.widget-content{
    display: flex;
}



</style>