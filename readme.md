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

1. Entrar no portal do Azure.

2. Clique no botão + Criar um recurso, procure Pesquisa de IA do Azure e crie um recurso de Pesquisa de IA do Azure com as seguintes configurações:

   * **Assinatura**: sua assinatura do Azure.
   * **Grupo de recursos**: selecione ou crie         um grupo de recursos com um nome exclusivo.
   * **Nome do serviço**: um nome exclusivo.
   * **Localização**: Escolha qualquer região disponível.
   * **Nível de preços**: Básico
3. Selecione Revisar + criar e, depois de ver a resposta Êxito da validação, selecione Criar.

4. Após a conclusão da implantação, selecione Ir para o recurso. Na página de visão geral da Pesquisa de IA do Azure, você pode adicionar índices, importar dados e pesquisar índices criados.

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


