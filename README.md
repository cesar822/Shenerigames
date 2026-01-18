# Shenerigames
Uma "revitalização" do antigo Shenerishop, mas agora focado em games.

## Equipe de desenvolvimento
| **Ordem** | **Nome** |
| - | ------------------- |
| 1 | César Costa Ribeiro |

## Atores do sistema

| **Ator** | **Descrição** |
| ------------- | ------------------- |
| Cliente       | Principal usuário do sistema, capaz de navegar pelos produtos, gerenciar seu carrinho, realizar uma compra simulada e fornecer avaliações. |
| Administrador | Usuário responsável pela gestão de produtos, estoque, descontos e moderação de avaliações. |

## Requisitos funcionais

|**ID**|**Ator(es)**|**Nome**|**Descrição**|
|------|--------|--------|-------------|
|REQ01|Cliente|Acessar páginas de produtos|Um cliente deve ser capaz de acessar a página de um produto que selecionar. Nela deve conter: nome, empresa, imagens do produto, descrição, preço (em caso de desconto, exibir o preço original riscado e o preço com desconto em destaque), avaliações, nota média, quantidade disponível em estoque e prazo estimado de entrega|
|REQ02|Cliente|Gestão de carrinho|Os produtos de um cliente, com sua quantidade já informada, devem ser adicionados ao carrinho. Ele deve informar quais produtos estão nele, quantos de cada tipo possui, o subtotal de cada tipo de produto e o total da compra. Nele o cliente pode: adicionar mais produtos ou quantidade, remover produtos ou quantidade, ir para a página de pagamento ou cancelar a compra|
|REQ03|Cliente|Sistema de pesquisa|Um cliente deve ser capaz de pesquisar numa aba o nome do produto ou da empresa cujo produto deseja. Deve ser capaz também de adicionar filtros a sua pesquisa. Os filtros serão: faixa de preço, marca, nota mínima e produtos com desconto|
|REQ04|Cliente|Fornecimento de avaliações|Um cliente deve ser capaz de avaliar um produto. Em suas avaliações, ele deve ter a possibilidade de: dar nota, deixar um comentário e dizer se recomenda o produto ou não. Avaliações já feitas podem receber votos positivos ou negativos para indicar sua utilidade ou relevância|
|REQ05|Administrador|Gestão de produtos|Um admin deve ser capaz de adicionar, editar ou desativar produtos do site e atualizar a quantidade no estoque|
|REQ06|Administrador|Gestão de descontos|Um admin deve ser capaz de aplicar descontos, seja percentual ou de valor fixo, a um ou vários produtos e informar o quanto tempo durará, seja via uma data de início e fim ou usando tempo de duração (pro caso de descontos relâmpagos)|
|REQ07|Administrador|Remoção de avaliações|Um admin deve ser capaz de remover avaliações|
|REQ08|Administrador, Cliente|Cadastro e autenticação|O sistema deve permitir que clientes e administradores criem contas e realizem login para acesso às funcionalidades restritas|
|REQ09|Cliente|Compra de produtos (simulação)|Um cliente deve ser capaz de comprar os produtos que estão em seu carrinho. Sendo redirecionado para uma página de pagamento que mostrará: quais produtos estão sendo comprados, total a pagar e prazo estimado de entrega|


## Regras de negócio

|**ID**|**Nome**|**Descrição**|
|------|--------|-------------|
|RN01|Compra apenas a clientes logados|Apenas clientes que estejam logados podem realizar a compra dos produtos (simulada). Caso um cliente encha o carrinho e clique para comprar, ele deve entrar na sua conta ou criar uma para enfim continuar com a ação|
|RN02|Unicidade dos carrinhos de compra|Os carrinhos de compras são únicos por cliente|
|RN03|Avaliações exclusivas para clientes logados|Apenas clientes que estejam logados podem fazer avaliações|
|RN04|Período dos descontos|Um admin só pode criar descontos que vão do dia atual para o futuro|
|RN05|Avaliação única por produto|Um cliente pode realizar apenas uma avaliação por produto|
|RN06|Produtos sem estoque não podem ser comprados|Produtos com quantidade zero em estoque não podem ser adicionados ao carrinho|
|RN07|Exclusividade para a criação de contas de administração|Apenas administradores podem criar contas de administração|

## Casos de uso

|**ID**|**Nome**|**Requisitos funcionais**|**Regras de negócio**|
|------|--------|-------------------------|---------------------|
|CSU01|Cadastro de contas e login|REQ08|RN07|
|CSU02|Acessar páginas dos produtos|REQ01|-|
|CSU03|Pesquisa de produtos via filtros e/ou texto|REQ03|-|
|CSU04|Sistema de carrinho de compras|REQ02|RN01, RN02, RN06|
|CSU05|Sistema de avaliações|REQ04|RN03, RN05|
|CSU06|Gestão de produtos|REQ05|-|
|CSU07|Gestão de descontos|REQ06|RN04|
|CSU08|Gestão de avaliações|REQ07|-|
|CSU09|Compra de produtos|REQ09|RN01|
