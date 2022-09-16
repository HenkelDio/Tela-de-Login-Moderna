# Criando uma tela de login moderna

Esse guia deseja ensinar como construir uma tela de login do zero com ferramentas gratuitas.<br>
Será usado trechos de código, comentários e imagens para explicação.<br>
Usaremos as tecnologias HTML5 e CSS3 para a construção da aplicação.<br>

(Esse guia é apenas Front-End, sem a utilização de Back-End. Apenas estilização e montagem)

## Pré-requisitos:

- Conhecer alguns recursos básicos das tecnologias [HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML) e [CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS).
- Saber usar algum IDE para desenvolvimento Web (recomendo: [VSCODE](https://code-visualstudio-com.translate.goog/?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt-BR&_x_tr_pto=sc))

# Iniciando

Coloquei todos os códigos na pasta "src". Então, caso precise acesse o código completo.<br>
Haverá algumas situações, onde o trecho do código não será explicado, por questões de não se aplicar a esse guia.<br>
Todas as imagens usadas estão na pasta "assets".

# Começando pelo HTML

Vamos iniciar adicionando o HTML em nossa página, ou seja, a estrutura do nosso documento.

```
<!DOCTYPE html>
<html lang="pt-br"> <!--Definindo o documento html e linguagem padrão-->
<head>
    <!--metadados da página-->
    <meta charset="UTF-8"> <!--define os carecteres como UNICODE-->
    <meta http-equiv="X-UA-Compatible" content="IE=edge"> <!--para página ser suportada no Internet Explorer-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!--Ajuda na resposividade do site-->
    <title>Tela de Login</title>
</head>
<body>

</body>
</html>
```

Dentro da tag <code>body</code>, adicionaremos uma <code>div</code> com a <code>class</code> <b>"container"</b>.

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tela de Login</title>
</head>
<body>

    <div class="container">

    </div>

</body>
</html>
```

A tag <code>div</code> tem como objetivo separar e organizar o conteúdo da página, como se fosses "caixinhas" com itens dentro.<br>
Já o atributo <code>class</code> coloca um identificador na <code>div</code>, mas tenha cuidado, esse identificador não é único. Para adicionarmos um identificador único, usamos o atributo <code>id</code>.
<br>
<br>
Agora, vamos adicionar mais duas <code>div</code> dentro da <code>div</code> <b>"container"</b>. A <b>img-side</b> e a <b>form-side</b>.

```
<body>

    <div class="container">

        <div class="img-side">

        </div>
        <div class="form-side">

        </div>

    </div>

</body>
```

A <code>div</code> <b>img-side</b> vai ser onde aplicaremos uma imagem e uma cor de fundo. Enquanto, a <b>form-side</b> será o lado que montaremos o formulário para o usuário preencher.
<br>
<br>
Vamos colocar nosso primeiro elemento em nossa página!

```
<body>

    <div class="container">

        <div class="img-side">
            <img src="/assets/mulher.png" alt="mulher">
        </div>
        <div class="form-side">

        </div>

    </div>

</body>
```

A tag <code>img</code> tem a função de adicionar uma imagem no documento.<br>
O atributo <code>alt</code> serve para colocarmos uma descrição na imagem para acessibilidade.
<br>
<br>
Dentro de <b>form-side</b>, vamos adicionar uma <code>div</code> com a <code>class</code> <b>titulo</b>, que será onde iremos adicionar os textos de título.<br>
Além disso, vamos colocar uma tag <code>form</code> que é uma opção melhor para formulários, ajuda na semântica do documento e no Back-End.

```
<div class="form-side">
    <div class="titulo">

    </div>
    <form>

    </form>
</div>
```

<br>
<br>

Agora, vamos adicionar mais elementos em nossa página.

```
<div class="titulo">
    <h2>Seja bem-vindo(a)!</h2>
    <p>Digite suas credencias para entrar em mundo mágico!</p>
</div>
```

Na <code>div</code> <b>titulo</b>, coloque um título na tag <code>h2</code> e um subtítulo na tag <code>p</code>.
<br>
<br>
Vamos montar nosso formulário de login dentro da tag <code>form</code>.

```
<form>
    <label for="in-email">Seu e-mail</label>
    <input type="email" name="in-email" class="in-email">
    <label for="in-password">Sua senha</label>
    <input type="password" name="in-password" class="in-password">
    <input type="button" value="Entrar" class="sub-entrar">
</form>
```

Nesta estrutura, foi usado a tag <code>label</code> que tem a função de rótulo no html, dentro da tag temos o atributo <code>for</code> que usamos para associar ao elemento de controle, como a tag <code>input</code>, que por sua vez é usado para os usuários interagirem.<br>
O elemento <code>input</code> tem vários tipos, como os que foram usados dentro do atributo <code>type</code>. Na nossa página, usamos os tipos, <b>email</b> para e-mails, <b>password</b> para senhas e <b>button</b> para acionar alguma ação.

<br>
<br>

Por fim, adicionaremos duas tags <code>a</code> abaixo do elemento <code>form</code>.

```
<form>
    <label for="in-email">Seu e-mail</label>
    <input type="email" name="in-email" class="in-email">
    <label for="in-password">Sua senha</label>
    <input type="password" name="in-password" class="in-password">
    <input type="submit" value="Entrar" class="sub-entrar">
</form>
<div><a href="#">Esqueci minha senha</a> ou <a href="#">Já tenho cadastro</a></div>
```

A tag <code>a</code> serve como link para outras páginas e urls. No valor do atributo <code>href</code> é passado o destino, como não temos nenhum, podemos colocar "#".
<br>
<br>

Terminamos toda estrutura HTML! Até agora, nossa página ficou assim:

![](assets\pagina_html.png)

Por enquanto, nada está em seu devido lugar, mas vamos mudar isso com o poderoso CSS.

# Estilização com CSS

Vamos abrir o arquivo de CSS e como estrutuda padrão, aplicaremos o seguinte código:

```
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

O <code>\*</code> serve para aplicarmos essa estilização para todos elementos do documento, incluindo o body e html.<br> Esse código irá redefinir a margem, a margem interna e o tamanho levará em conta a borda aplicada.
<br>
<br>
No elemento <code>body</code> aplicaremos como cor de fundo um roxo escuro (#10002B) e a fonte Segoe UI para todo documento.

```
body{
    background-color: #10002B;  /* cor de fundo*/
    font-family: 'Segoe UI';      /*fonte*/
}
```

<br>
<br>
Em nossa <code>div</code> <b>container</b> iremos aplicar as seguintes estilizações:

```
.container{
    width: 1100px;           /*largura do elemento*/
    height: 600px;           /*tamanho do elemento*/
    padding: 50px 50px;      /*margem interna: 50px em cima e em baixo e 50px dos lados*/
    margin: 80px auto;       /*centralizar elemento e 80px de margem externa em cima e em baixo*/
    display: flex;
    align-items: center;
    border-radius: 20px;     /*arredondamento das bordas de 20px*/
    background-color: #5A189A;
    box-shadow: 2px 2px 5px 5px rgb(19, 19, 19);
}
```

Apenas com esses códigos, temos:

![](assets\pagina_css1.png)
<br>
<br>
Agora, no elemento <b>img-side</b> e na imagem, aplicaremos:

```
.container .img-side{
    width: 50%;           /*largura com metade da largura da div container*/
    margin-right: 100px;  /*margem externa a direita de 100px*/
}

.container .img-side img{
    width: 100%;          /*100% de tamanho dentro da div img-side */
}
```

<br>
<br>
Na <code>div</code> <b>form-side</b> e na <code>div</code> <b>titulo</b>, vamos aplicar:

```
.container .form-side{
    text-align: center;       /*centralizar todos os textos do elemento*/
    height: 350px;
    color: white;           /*cor do texto da div*/
}

.container .form-side .titulo{
    margin-bottom:30px;       /*margim externa para baixo de 30px*/
}

.container .form-side .titulo h2{
    font-size: 40px;          /*tamanho de fonte*/
}

.container .form-side .titulo p{
    color: #e5b8ff;
}
```

<br>
<br>
No elemento <code>form</code> e nos inputs de <b>e-mail</b> e <b>password</b>, utilizaremos os seguintes estilos:

```
.container .form-side form{
    display:inline-block;
    width: 400px;
    text-align: left;
}

.container .form-side form label{
    font-weight: bold;             /*aplicar negrito no texto*/
    color: #E0AAFF;
}

.in-email, .in-password{           /*acessando os inputs*/
    width: 400px;
    height: 40px;
    padding-left: 20px;            /*margem interna a esquerda de 20px*/
    outline: none;                 /*borda externa desabilitada*/
    margin-bottom: 20px;
    font-weight: 600;              /*peso da fonte em 600*/
    border-radius: 5px;
    border: none;                  /*borda desabilitada*/
}
```

<br>
<br>
No <code>button</code> e na <code>div</code> <b>link</b>, aplicaremos:

```
.sub-entrar{
    width: 400px;
    height: 40px;
    border-radius: 10px;
    border: none;
    font-weight: bold;
    font-size: 20px;
    cursor: pointer;
    color: #3C096C;
    background-color: #C77DFF;
    margin-bottom: 20px;
}

.container .form-side .link{
color: white;
}

.container .form-side .link a{
color: #E0AAFF;
}
```

<br>
<br>

No fim, teremos nossa página completa:
![](assets\pagina_css2.png)

<br>
<br>
