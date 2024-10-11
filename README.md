# Automação de Cadastro de Produtos no Sistema 🛠️

Este projeto realiza a automação do processo de login e cadastro de produtos em um sistema web, utilizando a biblioteca **PyAutoGUI** para simular interações com o navegador e a interface do usuário. A automação é particularmente útil para empresas que precisam cadastrar produtos em grandes volumes.

## Descrição do Projeto

A automação segue o fluxo de entrar no sistema, fazer login e cadastrar produtos automaticamente a partir de um arquivo `produtos.csv`. O script automatiza o processo de entrada de dados, preenchendo cada campo de cadastro de forma eficiente e repetitiva.

### Passo a Passo do Projeto

1. **Abrir o Navegador e Entrar no Sistema**
    - O script abre o navegador (Chrome) e acessa a página de login da empresa.
    - URL de login: [https://dlp.hashtagtreinamentos.com/python/intensivao/login](https://dlp.hashtagtreinamentos.com/python/intensivao/login)

2. **Fazer Login no Sistema**
    - O script preenche os campos de email e senha e realiza o login no sistema.
    - Email e senha são inseridos automaticamente utilizando **PyAutoGUI**.

3. **Importar a Base de Produtos**
    - A base de dados dos produtos que serão cadastrados é carregada a partir de um arquivo CSV (`produtos.csv`) usando **Pandas**.

4. **Cadastro de Produtos**
    - O script percorre cada linha da tabela de produtos e preenche os campos no formulário de cadastro do sistema:
      - Código
      - Marca
      - Tipo
      - Categoria
      - Preço Unitário
      - Custo
      - Observações (caso existam)
    - Após preencher os campos, o produto é enviado (cadastrado) e o script continua com o próximo produto até o final da tabela.

### Pré-requisitos

Certifique-se de ter as seguintes bibliotecas instaladas:

1. **PyAutoGUI** (para automação de interface gráfica):
   ```bash
   pip install pyautogui
2. **Pandas** (para manipulação de dados):
   ```bash
   pip install pandas
3. Tenha o arquivo produtos.csv com a seguinte estrutura:

codigo	marca	   tipo	   categoria	preco_unitario	custo	  obs
123	    Marca X	 Tipo 1	 Categoria	  99.99	        60.00	   Nenhuma
456	    Marca Y	 Tipo 2	 Categoria	  199.99	      120.00	 Em promoção

## Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/BrunoH4ds/cadastro-produtos-automacao.git

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt

3. Garanta que você tem o arquivo produtos.csv na mesma pasta do projeto.

4. Execute o script:

   ```bash
   python cadastro_produtos.py

O navegador será aberto, o login será realizado automaticamente, e os produtos serão cadastrados um a um no sistema.

## Observações
Posição dos elementos na tela: Certifique-se de que as coordenadas de clique (x, y) no script correspondem à sua tela e resolução. Caso contrário, você pode ajustar manualmente utilizando o comando do arquivo mouseposition Isso permitirá que você veja as coordenadas exatas do ponto onde o mouse está assim podendo fazer a alteracao no arquivo principal.

Tempos de espera: O script utiliza a função time.sleep() para dar pausas entre ações, garantindo que o sistema tenha tempo para carregar as páginas e campos antes da próxima interação. Esses tempos podem ser ajustados conforme necessário.

