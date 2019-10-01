#home-accounting

Breve Especificação:

Gerenciador de itens de uma listagem com 3 visões:
 - Visão Geral: Lista todos os itens cadastrados na lista de itens;
 - Visão Obtidos: Lista apenas os itens da listagem geral que já foram obtidos;
 - Visão Não-Obtidos: Lista apenas os itens da listagem geral que não foram obtidos; 

Cadastro de Item:
	Descrição do Item; *
	Marca;
	Valor médio; *
	Valor real;
	Link de referência;
	Obtido? - flag; * (default = false)

* Campos obrigatórios no cadastro do item;

A visão deve ser alterada por um combobox (lista flutuante) que irá listar as visões possíveis. Ao alterar a visão, automaticamente o browser deve atualizar a listagem dos itens para corresponder corretamente com a visão solicitada; 

Na tela deverá ter um campo superior em caixa alta que determina o valor total dos itens da listagem correspondente. 

	Ex: Se a visão escolhida for Obtidos - Então o valor total que deverá ser exibido é a soma dos valores reais dos itens que possuem flag 	obtido = true;
		Se a visão escolhida for Não-Obtidos - Então o valor total que deverá ser exibido é a soma dos valores médios dos itens que possuem flag obtido = false;
		Se a visão escolhida for Geral - Então o valor total que deverá ser exibido é a soma dos valores reais dos itens que possuem flag obtido = true com o valor médio os itens que possuem a flag false; 

Obs: Valor real: Campo obrigatório caso o usuário altere a flag obtido para true;

Em cada linha/item deve ter um botão de alterar, que ao ser acionado possibilita a alteração do item; 
Em cada linha/item deve ter um botão de remover, que ao ser acionado possibilita a exclusão do item;

Detalhes do fluxo de versionamento GIT:

  * Trata-se de uma adaptação do GitFlow:
    - master : essa branch deve conter apenas todas as features testadas e estáveis;
    - develop : todas as features devem ser criadas a partir da develop;
    - feature/000x : todas as features devem ser criadas com essa nomeclatura e devem ser criadas a partir da develop;
    - hotfix/000x : hotfixies são branches criadas para corrigir algum erro ou bug que por acaso for identificado no processo e estará associado a um identificador de task; 
    
    PS: 000x -> é um identificador de taks; as branches estarão associadas a uma task no trelo e a task terá esse identificador; É possível existir uma feature/000x e uma hotfix/000x, mas nunca duas features/000x partindo do principio de que serão um para um e que o próprio git não permite branches com nomes repetidos no repositório; 
    Ex: feature/0001 -> Criar tela de login;
      No Trelo existirá uma task de id 0001 - Criar tela de login;
      Caso um erro seja identificado nessa tela uma branch hotfix(hotfix/0001) pode ser criado para correções desses erros; 
      Com isso sempre saberemos a que task no trelo cada branch está associada e evitamos de criar várias branches desnecessariamente   para resolver o mesmo problema.
    



