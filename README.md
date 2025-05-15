# Resumidor de Notícias com Gemini

Este projeto em Python utiliza a API do Gemini do Google AI Studio para resumir o conteúdo de notícias a partir de links da web. Ele permite que o usuário insira um link de uma notícia e receba um resumo conciso dos principais pontos.

## Funcionalidades

* **Extração de Texto de Links:** O script é capaz de acessar o conteúdo textual de páginas da web fornecidas através de um link.
* **Resumo Sucinto:** Utiliza o modelo `gemini-2.0-flash` com uma configuração específica para gerar resumos curtos e focados nos principais pontos do texto.
* **Ignora HTML:** O modelo é instruído a ignorar quaisquer comandos HTML presentes no texto da página, focando apenas no conteúdo textual puro.
* **Enumeração de Pontos Principais:** Ao final do resumo, o modelo lista os principais pontos identificados no texto original.
* **Interface de Linha de Comando:** O projeto interage com o usuário através da linha de comando, solicitando o link da notícia e exibindo o resumo.
* **Loop Interativo:** Permite que o usuário insira múltiplos links para resumir diferentes notícias sem precisar reiniciar o script. O programa encerra quando o usuário digita "fim".

## Pré-requisitos

Antes de executar o código, você precisará:

1.  **Criar uma conta no Google AI Studio:** Acesse [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey) e siga as instruções para criar uma conta e gerar uma **API Key**.
2.  **Instalar as dependências:** Certifique-se de ter as seguintes bibliotecas Python instaladas. Você pode instalá-las usando o `pip`:

    ```bash
    pip install google-generativeai google-colab requests
    ```

## Configuração

1.  **Armazenar a API Key:** O script utiliza o `google.colab.userdata` para acessar a API Key de forma segura no ambiente Google Colab. Se você estiver executando o código localmente ou em outro ambiente, precisará configurar a variável de ambiente `GOOGLE_API_KEY`.

    **No Google Colab:**
    * No painel esquerdo, clique no ícone de chave (Secrets).
    * Crie um novo segredo com o nome `GOOGLE_API_KEY` e cole sua API Key do Google AI Studio no campo de valor.

    **Localmente (não recomendado para segurança em longo prazo):**
    Você pode definir a variável de ambiente diretamente no seu terminal antes de executar o script:

    ```bash
    export GOOGLE_API_KEY="SUA_API_KEY"
    ```

    **Melhor prática localmente (usando `.env`):**
    Crie um arquivo chamado `.env` no mesmo diretório do seu script e adicione a seguinte linha:

    ```
    GOOGLE_API_KEY=SUA_API_KEY
    ```

    Em seguida, você precisaria adicionar algumas linhas ao seu código Python para carregar as variáveis de ambiente do arquivo `.env` (usando uma biblioteca como `python-dotenv`).

2.  **Executar no Google Colab (opcional):** Se você estiver usando o Google Colab, o ambiente já possui algumas dependências pré-instaladas. Basta conectar-se a um runtime e executar as células de código.

## Como Usar

1.  **Execute o script Python.**
2.  Quando solicitado na linha de comando, **informe o link da notícia** que você deseja resumir e pressione Enter.
3.  O script irá processar o link, extrair o texto e enviar para a API do Gemini.
4.  O resumo gerado, juntamente com os principais pontos enumerados, será exibido na tela.
5.  Você será solicitado a inserir outro link. Para encerrar o programa, digite `fim` e pressione Enter.

## Exemplo de Uso

Informe o link da notícia ou digite "fim" para encerrar: https://news.example.com/article1
Texto da página obtido com sucesso!
Resumo: Este artigo fala sobre um novo estudo que descobriu um aumento significativo na população de abelhas em áreas urbanas devido a jardins e telhados verdes. Os pesquisadores ficaram surpresos com a adaptabilidade das abelhas a ambientes urbanos.

Principais pontos:

Novo estudo revela aumento da população de abelhas em cidades.
Causa principal: presença de jardins e telhados verdes.
Surpreendente adaptabilidade das abelhas a áreas urbanas.
Informe o link da notícia ou digite "fim" para encerrar: https://another-news.com/tech-update
Texto da página obtido com sucesso!
Resumo: A principal empresa de tecnologia lançou um novo smartphone com câmera aprimorada e bateria de longa duração. O preço inicial é de $799 e estará disponível na próxima semana.

Principais pontos:

Lançamento de novo smartphone por grande empresa de tecnologia.
Destaques: câmera aprimorada e bateria duradoura.
Preço inicial: $799.
Disponibilidade: próxima semana.
Informe o link da notícia ou digite "fim" para encerrar: fim


## Observações

* A qualidade do resumo pode variar dependendo da complexidade e da estrutura do texto da página web.
* Certifique-se de que o link fornecido seja de uma página web acessível e contenha texto relevante para ser resumido.
* O tempo de resposta pode depender da velocidade da sua conexão com a internet e da carga da API do Gemini.

## Autor

[lcllima3012]

Sinta-se à vontade para contribuir com melhorias ou reportar problemas!
