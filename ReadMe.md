# StartLess
Essa é uma plataforma com objetivo de auxíliar no desenvolvimento, escrita e organização de arquivos CSS e pastas de projetos Web.

Nós estudamos e adaptamos para nossa realizade/necessidade alguns padrões que encontramos na comunidade que são: BEM, SMACSS e Namespace.

## Why?
Essa plataforma foi criada para auxiliar no desenvolvimento de sites.

LESS

## Configuração
Adicione os arquivos LESS e CSS no seu projeto e referêncie o link:

```html
<link rel="stylesheet" href="Styles/main.min.css"/>
```

## Tabela de Conteúdo

* [Cabeçalho Projeto](#cabeçalho-projeto)
* [Base](#base)
    - [Base SMACSS](#base-smacss)
    - [Base BEM](#base-bem)
    - [Base Namespace](#base-namespace)
* [Exemplos](#exemplos)

## Cabeçalho Projeto
Essa é um cabeçalho padrão com informações básicas do projeto

LESS (PROJETO) + (CLIENTE)

- @Trabalho - E-commerce 2.0
- @Dispositivos - Smartfones e Desktop
- @Site - www.urldocliente.com.br
- @Autor - Thiago Rusty <rusty@pwi.com.br>
- @Data - 06/10/2016
- @Versão - 1.0

INFORMAÇÕES TÉCNICA

- @Framework - Bootstrap 3.3.7 / Jquery 1.4
- @Tela - Wide ou Boxed
- @Fonte - Open Sans - WebFont

## Base

### Base SMACSS
.b: base
	cores, variaveis reutilizáveis, tipografia reset
.c: components
	pequenos componentes como botão, formularios, modals
.h: helpers
	funções, mixins e helpers como blocos reutilizáveis
.l: layout
	definições de estilo para header, footer e grid
.t: theme
	definição de temas caso o site possua variações

### Base BEM
base
	.b-block
	.b-block__element
	.b-block--modifier

components
	.c-block
	.c-block__element
	.c-block--modifier

helpers
	.h-block
	.h-block__element
	.h-block--modifier

layout
	.l-block
	.l-block__element
	.l-block--modifier

theme
	.t-block
	.t-block__element
	.t-block--modifier
### Base Namespace
base
	.{namespace}-b-block
	.{namespace}-b-block__element
	.{namespace}-b-block--modifier

components
	.{namespace}-c-block
	.{namespace}-c-block__element
	.{namespace}-c-block--modifier

helpers
	.{namespace}-h-block
	.{namespace}-h-block__element
	.{namespace}-h-block--modifier

layout
	.{namespace}-l-block
	.{namespace}-l-block__element
	.{namespace}-l-block--modifier

legenda
	t-  tema
	ex- externo
	is- estado
	hk- hack
	js- javascript

## Exemplos

### URL Variável
O parametro @ImagesUrl se encontra no 

```html
<style>
    .icon {
        background: url("@{ImagesUrl}/icon.png") no-repeat;
    }
</style>
```

### Extend (PlaceHolder)
```css
/*EXTEND (PLACEHOLDER)*/
	.animal {
		width: 100%;
		background-position: center center;
		background-size: cover;
		background-repeat: no-repeat;
	}

	.bear {
		&:extend(.animal);
		background-color: black;
	}

	.dog {
		&:extend(.animal);
		background-color: brown;
	}

/*EXTEND OUTPUT*/
	.animal, .bear, .dog {
		width: 100%;
		background-position: center center;
		background-size: cover;
		background-repeat: no-repeat;
	}

	.bear {
		background-color: black;
	}

	.dog {
		background-color: brown;
	}
```







/*
Project Name - Client Name

	- @Work		    	Custom System
	- @Devices  		Smartfones, Tables and Desktop
	- @Site 			http://www.customsystem.com
	- @Author			Technical Manager <your@email.com>
	- @Date 			17/12/2018
	- @Version			1.0


TECHNIQUES INFORMATIONS

	- @Framework		    If there are some in use (Bootstrap 3.3.7 / Jquery 3.1.1)
	- @Screen				Boxed | Full-Size
    - @Web Typography	 	Open Sans - WebFont / Raleway - Incorporated
*/






/* #region Order of properties */
    .Class {
        @Mixins;      MIXINS AND EXTENDS SHOULD BE IN THE FIRST PLACE BECAUSE OF CSS OVERWRITING
        @Extends;     MIXINS AND EXTENDS SHOULD BE IN THE FIRST PLACE BECAUSE OF CSS OVERWRITING
        [Positions];
        [Dimensions];
        [Spacings];
        [Borders];
        [Text Styles];
        [Colors];
        [Backgrounds];
    }
/*#endregion */

/*#region Namespaces */
        u   -   utilitario
        t   -   tema
        ex  -   externo
        hk  -   hack
        is  -   state @Modal state. Is open or is closed.    
        js  -   javascript
        p   -   print    
/*#endregion */

/*#region Examples */
    
    /*#region EXTEND */

        /*
            .testAnimal {
                width: 100%;
                background-position: center center;
                background-size: cover;
                background-repeat: no-repeat;
            }

            .testBear {
                &:extend(.testAnimal);
                background-color: black;
            }

            .testDog {
                &:extend(.testAnimal);
                background-color: brown;
            }

        */

    /*#endregion */

    /*#region MIXIN WITH EXTEND */

        /*
            .anchorClass {
                .padding(10px, 15px, 25px, 3);
            }

            .testAnchor {
                &:extend(.anchorClass);
            }
        */

    /*#endregion */

    /*#region IF (WHEN) */

        /*
            .testIfTheme (@mode) when (@mode = "dark") {
                background: #fff;
            }

            .testIfTheme (@mode) when (@mode = "light") {
                background: #c3c3c3;
            }

            .testIfTheme (@mode) {
                border: thick solid orange;
                color:#fff;
                margin-top:10px;
            }

            .testIfTheme {
                padding: 10px;
                .testIfTheme("dark");
            }
        */

    /*#endregion */

/*#endregion */