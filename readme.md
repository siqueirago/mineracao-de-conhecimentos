# Mineração de Conhecimento: Desenvolvendo um Índice de Pesquisa de IA do Azure 
## Introdução
No cenário atual de negócios, entender e atender às necessidades do cliente é essencial para o sucesso de qualquer empresa. Como  por exemplo uma rede nacional de cafés, 
a *Fourth Coffee*  que está comprometida em oferecer experiências excepcionais aos seus clientes. Para alcançar esse objetivo, a empresa  precisa acompanhar e monitorar as  percepções e os feedbacks dos clientes.

Neste contexto, como  se fosse membro da equipe da Fourth Coffee, fui encarregado de desenvolver uma solução inovadora que facilite a extração de insights valiosos a partir das avaliações dos clientes. 
Com o objetivo de agilizar esse processo e torná-lo mais eficiente, optei por criar um índice de Pesquisa de IA do Azure, uma ferramenta poderosa baseada na plataforma de inteligência artificial
da Microsoft.

## Objetivos do Projeto


* Criar recursos do Azure
* Extrair dados de uma fonte de dados
* Enriquecer dados com habilidades de IA
* Usar o indexador do Azure no portal do Azure
* Consultar o índice de pesquisa
* Revisar resultados salvos em um Knowledge Store
## Procedimentos

O primeiro passo deste projeto será criar os seguintes recursos usando uma assinatura do Azure:

* **Um recurso de Pesquisa de IA do Azure**, que gerenciará a indexação e a consulta.
* **Um recurso de serviços de IA do Azure**, que fornece serviços de IA para habilidades que sua solução de pesquisa pode usar para enriquecer os dados na fonte de dados com insights gerados por IA.
* **Uma conta de armazenamento com contêineres de blob**, que armazenará documentos brutos e outras coleções de tabelas, objetos ou arquivos.

## Criando o recurso de Pesquisa de IA do Azure

1. Entrar no [Portal do Azure](https://portal.azure.com/).

2. Clique no botão + Criar um recurso, procure Pesquisa de IA do Azure e crie um recurso de Pesquisa de IA do Azure.
   ![IA Search](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/4c1bb21c-5ab3-4188-8fe7-62d33a30fd0e)


   
   **Faça  as seguintes configurações:**

   * **Assinatura**: sua assinatura do Azure.
   * **Grupo de recursos**: selecione ou crie         um grupo de recursos com um nome exclusivo.
   * **Nome do serviço**: um nome exclusivo.
   * **Localização**: Escolha qualquer região disponível.
   * **Nível de preços**: Básico
4. Selecione Revisar + criar e, depois de ver a resposta Êxito da validação, selecione Criar.

5. Após a conclusão da implantação, selecione Ir para o recurso. Na página de visão geral da Pesquisa de IA do Azure, você pode adicionar índices, importar dados e pesquisar índices criados.

## Criando  um recurso de serviços de IA do Azure

1. Retornando à home page do portal do Azure.Criar um novo recurso, desta vez, criar um plano de **Serviços de IA do Azure**, com as seguintes configurações:
  
   * **Assinatura**: sua assinatura do Azure.
   * **Grupo de recursos**: o mesmo grupo de recursos que seu recurso de Pesquisa de IA do Azure.
   * **Região**: o mesmo local que seu recurso de Pesquisa de IA do Azure.
   * **Nome**: Um nome exclusivo.
   * **Nível de preços**: Standard S0
   * **Ao marcar esta caixa reconheço que li e compreendi todos os termos abaixo**: Selecionado
2. Selecionar Revisar + criar. Depois de ver a resposta Validação aprovada, selecione Criar.
* Aguarde a conclusão da implantação e exiba os detalhes da implantação.
  
## Criar uma conta de armazenamento

1. Retorne à home page do portal do Azure e selecione o botão **+ Criar um recurso**.
* Procure uma conta de armazenamento e crie um recurso de conta de armazenamento com as seguintes configurações:
  
  * **Assinatura**: sua assinatura do Azure.
  * **Grupo de recursos**: o mesmo grupo de recursos que os recursos da Pesquisa de IA do Azure e dos serviços de IA do Azure.
  * **Nome da conta de armazenamento**: um nome exclusivo.
  * **Localização**: Escolha qualquer local disponível.
  * **Desempenho**: Standard
  * **Redundância**: Armazenamento localmente redundante (LRS)
    
* Clique em **Rever** e, em seguida, clique em **Criar**. Aguarde a conclusão da implantação e vá para o recurso implantado.
* Na conta de Armazenamento do Azure que você criou, no painel de menu esquerdo, selecione **Configuração** (em **Configurações**).
* Altere a configuração de Permitir acesso anônimo de Blob para **Habilitado** e selecione **Salvar**.
  
## Carregar documentos no Armazenamento do Azure
1. No painel de menu esquerdo, selecione Contêineres.
   
![Conteiner](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/88ea8b55-5d19-46f4-8294-66c4a571f948)

2. Selecione + Contêiner. Um painel do lado direito é aberto.

    **Insira as seguintes configurações e clique em Criar:**
    * **Nome**: café-comentários
    * **Nível de acesso público**: Contêiner (acesso de leitura anônimo para contêineres e blobs)
    * **Avançado**: sem alterações.
3. Em uma nova guia do navegador, baixe as revisões de café compactadas do e extraia os arquivos para a pasta de comentários.https://aka.ms/mslearn-coffee-reviews

4. No portal do Azure, selecione seu contêiner de avaliações de café. No contêiner, selecione Carregar.
![carregar doc](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/8c6cbd94-81d5-4936-8a7d-84feff8ffb01)

## Indexar os Documentos
1. No portal do Azure, navegue até seu recurso de Pesquisa de IA do Azure. Na página Visão geral, selecione Importar dados.
![Indexador](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/0b795600-3356-4165-9439-6690bfa1d123)

2. Selicione o nome do indexador para ver mais detalhes
![coffee index](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/1b797bb8-26c2-4ed6-9f80-7d0e533c3f18)

## Consultar o indice
1. Na página Visão geral do serviço de Pesquisa, selecione Gerenciador de pesquisa na parte superior da tela.
2. Observe como o índice selecionado é o índice de café que você criou. Abaixo do índice selecionado, altere a exibição para JSON view.
![chicago](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/0f31d63b-bc09-42dd-a2a5-c32b8630f63f)

## Revisar o repositorio de conhecimento
1. No portal do Azure, navegue de volta para sua conta de armazenamento do Azure.

2. No painel de menu esquerdo, selecione Contêineres. Selecione o contêiner de armazenamento de conhecimento.
3. Selecione qualquer item e clique no arquivo **objectprojection.json**.

![json2](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/44f58157-5e10-47f1-a018-92f498eb459d)

4. Selecione qualquer um dos **.jpg arquivos**. Selecione **Editar** para ver a imagem armazenada do documento. Observe como todas as imagens dos documentos são armazenadas dessa maneira.

![img](https://github.com/siqueirago/mineracao-de-conhecimentos/assets/152822615/57248bb9-e1d0-41ba-a352-eb5ddeea524a)

## Conclusão
Durante este laboratório consegui realizar o passo a passo do projeto proposto. Teve alguma dificuldade mas nada de viesse impedir o deseolvolvimento desse projeto.
Adqueri bastante conhecimento, criei os recursos necessários, fiz a manipulação dos dados e visualizar os resultados. Foi batante proveitoso espero que a cada dia 
melhorar.




   







