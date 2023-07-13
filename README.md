# Sobre inputs no html

## ``<input>``  
- Um dos mais usados em formulários
- Aceita os mais diversos tipos de dados
- Um dos mais poderosos e complexos
- Elevado numeor de combinações

### Atributos mais utlizados da tag input
- type 
    * define o tipo do input e dependedo do tipo adiciona 
            regras de validação como por exmeplo a obrigação do "@" no type email;
- name 
    * da um nome ao o input;
- id 
    * da uma identifica o elemento;
- autocomplete 
    * da a opção de auto completar um campo com informações
            armazenadas no browser;
- autofocus 
    * traz foco a um campo assim q é aberta a pagina, só 
            funciona em um campo pos n é possivel focar em amis de um campo/elemento
            de uma vez;
- readonly 
    * define o elemento como apenas leitura, não possibilitando
        a edição do conteudo com este atributo;
- value 
    * aidicina um valor do campo;
- name 
    * util para avisa o banco de dados do que é essa informação
        que esta sendo enviada;
- form 
    * normalmente utilizado para associar um input/elemento a
        um formulario especifico, nele é colcoado o id do form;
- required 
    * é um campo que é obrigatorio para o envio do formulario
    * funciona em quase todos o navegadores;
        
        VERIFICAR A COMPATIBILIDADE DOS ATRIBUTOS NO (caniuse.com)

- placeholder 
    * deixa um texto dentro do campo para exemplo do deve ser escrito no campo;
- <label> 
    * é como se fosse o titulo para o campo, muito bom para acessibilidado
    *utiliza o 'for' para indicar a qual elemento ele é associado
        
        ------------------------------------------------------------
## ``<input type="password">``
        
- Colocar uma senha de maneir segura
- Esconde o que esta sendo digitado
- o estilo da apresentação do campo, dependeo do User Agent(estilo definido pelo browser)
        
### Atributos do input password
        
- minlenght / maxlength
    * O numero minimo-maximo de caracteres para este campo
- size
    * O numero aceitavel de caracxteres que este campo deve conter
- pattern
    * Expressão regular para validar o que esta sendo digitado
    * Altamente recomentado o uso de um padrão de seguraça alto de senhas
    * exemplo: queremos que a senha contenha caracteres hexadecimais com o limite de no minimo 4 caracteres e no maximo 8
        * ``pattern="[0-9a-fa-f] {4,8}"``
        * a parte entre colchetes dita o minimo e maximo de caracteres e a parte entre o simbolo de vetors é o hexadecimal definido
- title
    * pode ser como a mensagem de erro avisando o que mais esta faltando no caso da senha.
- autocomplete 
    * on = permite a sugestão de: new-password ou current-password
    * off = desabilita a opção de automplete
    * new-password = o navegado pdera sugerir uma nova senha

## ``<input type="email">``
- Espera que o usuario digite um email
- Ira validar se o valor digitado é um email

### Atributos do input email

- placeholder
- readonly/ didabled
- value
- required
- multiple
    * O campo ira receber 1 ou mais email, separado por vírgulas
- minlength / maxlength
    * O minimo/maximo de caracteres q o email deve ter
- size
    * Valor nimerico indicando quantos caracteres esse campo deve ter
- pattern
    * Uso de expressão regular para validar o campo
    * exemplo: o usuario só podera colocar email do dominio com ``.com.br``
        *`` pattern=".+@.+\.com\.br"``
        > O ``".+"`` significa qualquer caracter mais os que vierem após, sendo que o ``"."`` é qualquer caracter e o simbolo ``"+"`` possibilita adicinar mais carcteres depois
- list
    * O id de uma tag <datalist> que esta no mesmo documento
    * ``<datalist>`` íra conter uma lista de valores pré definidos
    a fim de sugerir ao usuario, quais valores estão desponiveis
    * Os valores do ``<datalist>`` que não forem compativeis com o campo, não serão apresetados como sugestão
    * em outra palavras ele permite ao desenvolvedor criar uma lista com email ou explos de email disponoveis, bom utilizado para dar exemplos como ``"@exemplo.com.br"``, ``"@exemplo.com"``, sugerindo  finais de email compativeis com o site.
             
## ``<input type="url">``

- Espera que o usuario digite uma url
- Irá validar se o valor digitado é uma url

### Atributos do input url

- placeholder
- readonly / desable
- value
- required
- minlenght / maxlenght
- size
- pattern
    * exemplo: o usuário só pode colocar dominios ``.com.br``
    * ``pattern=".*\.comz.br.*"``
- title
    * faz um papel de aviso;
- list
    * o id de uma tag ``<datalist>`` que esta no mesmos documento
    * ``<datalist>`` irá conter uma lista de valores pré definifos a fim de sugerir ao usuário, quais estão disponiveis
        * os valoees do ``<datalist>`` que não forem compativeis com o campo não serão apresentados como sugestão
- spellchech
    * Habilitar a verificação ortografica para este input

## ``<input type="file">`` 

- Usuário poderá escolhe 1 ou mais arquivos para enviar

### Atributos

- value
    * Contem o arquivo a ser enviado

- accept
    * Descreve que tipos de arquivos serão aceitos
    * exemplo: ``.doc``, ``.docx``, ``.pdf``, ``audio/*``, ``image/*``, ``image/png``, ``.png``

- files
    * A lista de arquivos ou arquivos

- multiple
    *permite o envio de múltiplos arquivos

### Envio dos arquivos

para o envio dos arquivos é necessario um fomulario com metodo POST e o atributo enctype como "multipart/from-data"

## ``<input type="color">``

- interface para celecionar cor
- Color picker

### Atributos

- value: RGB
    * se invalido, o preto será exibido
- list (não funciona em alguns navegadore especialmente androids) 
    * o id de uma tag ``<datalist>`` que está no mesmo documento
    * ``<datalist>`` irá conter uma lista de valores pré definidos a fim de apresentar cores ao usuario
        * os valores do ``<datalist>`` que não forem compativeis com o campo

## ``<input type="checkbox">``

- caixas que podem ser marcadas
- selecionar um valor para envio
- se não selecionado, não ira ser enviado nenhum dado

### Atributos

- globais
- value
    * Valor que aquele campo contem
    * se não estiver presente, o prsão é 'on'
- checked
    * para deixar o campo marcado por padrão

## ``<input type="hidden">`` 

- invisível ao usuario
- será enviado com o formulario
- não recebe foco
- leitores de tela não percebem esse campo

    codigo deste input:  ``<input type="hidden" id=" timestamp" value="tempo">``
    
## ``<input type="radio">``

Projetado para seleciona uma unica opção de um grupo de opções

### Atributos

- checked
    * indica que o campo foi marcado
- value
    * valor que aquele campo/opção contem

## ``<input type="textarea">``

- Quando queremos textos de mais de uma linha 
- util para textos grande, como um campo de sobre mim num form de cadastro

### Atributos

- id;
- name;
- rows e cols: altera o tamanho do campo;
- maxlenght/minlenght;
- wrap: o texto passa do limite do camp e a quebra de linha é feita apensa quando o usuario aperta a tecla 'ENTER' no teclado; 
- outros comuns aos ``<input>``s
    - ``autocomplete``, ``autofocus``, ``disabled``, ``placeholder``, ``readonly``, ``form``, ``required``

## ``<select>`` 

- Controle que fornece um menu de opções

### ``<option>``
- Contém as opções a serem selecionada
- Atributos necessario
    - value

### Atributos únicos
- multiple
    * Habilita multipla opções
- size
    * Quando opções visíveis

### ``<optgroup>``

- Serve para agrupar as ``<option>``s
- Sempre deve estar dentro do ``<select>`` e acompanhado do ``<option>``

## ``<input type="search">``

- Para campos de busca
- É igual ao campo do tipo 'text', mas pode ser um poudo diferente depedendo do User Agent

### Atributos

- list/``<datalist>``
- pattern
- aria-label

## ``<input type="range">`` 

- Controle para selecionar um valor numerico
- Slider ou dial control

### Atributos

- min/max
- step: passos aplicado quando se mexe o slider por exemplo de 1 em 1, 0,1 em 0,1 etc.
- value

## ``<input type="date">`` 

- Ficar de olho no caniuse.com para saber se funciona em certos browser

