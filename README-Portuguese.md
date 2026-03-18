# First Contrib Search


TLDR; Experimente [aqui](https://first-contrib.surge.sh)!

![First Contrib App](./github.png)

## Por que este projeto?

Como programador que deseja fazer sua primeira contribuição para um projeto de código aberto, às vezes pode ser difícil encontrar o projeto certo que corresponda às suas expectativas e habilidades.

Graças a alguns projetos como a [lista incrível](https://github.com/MunGell/awesome-for-beginners), você ainda pode encontrar listas *estáticas* de projetos que procuram desenvolvedores.

Indo além, se você deseja pesquisar problemas que podem ser tratados por iniciantes com o [Github Search Engine](https://github.com/search/advanced), você ainda precisa saber qual rótulo é usado por cada repositório para direcionar iniciantes.


## A Resposta

Este aplicativo tenta responder a este problema fornecendo um mecanismo de busca simples que direcionará todos os problemas com rótulos relacionados a *iniciantes*. Por enquanto, aproximadamente 50 rótulos diferentes estão listados neste [arquivo](https://github.com/GaelS/first-contrib-app/blob/master/src/labels.js).

E porque fazer um mecanismo de pesquisa pode ser mais legal do que parece, tentei seguir minhas vibrações internas dos anos 80 para fornecer um estilo *Miami Vice*/*GTA Vice City* :)

## Quais problemas encontrei ao longo do caminho?

 - Eu queria usar a API GraphQL fornecida pelo Github porque ela reduz drasticamente o número de chamadas de rede. No entanto, ela não pode ser chamada sem autenticação. Portanto, como usuário, você deve estar autenticado no Github para usar este aplicativo.

 - Principal desvantagem: ao pesquisar problemas por rótulo no Github, não podemos usar o operador "OR". Basicamente, não podemos pesquisar problemas com rótulos *GOOD FIRST CONTRIBUTION* **OU** *UP FOR GRABS* em uma consulta. Portanto, o truque para obter os problemas que podem ser de interesse é consultar **repositórios** que têm **problemas** correspondentes à nossa lista de rótulos. A infeliz consequência é que a lista de problemas listados em um repositório às vezes pode estar vazia... o que às vezes leva a obter uma lista de 20 repositórios sem nenhum problema para exibir... Essa é a razão pela qual o botão *buscar mais* pode precisar ser pressionado várias vezes antes de encontrar novos problemas para exibir...
 Uma ideia ingênua minha foi consultar novamente uma nova lista de repositórios quando nenhum problema é retornado, mas lançar solicitações de rede recursivamente não parece uma boa ideia... ahem...

## A Stack

As principais bibliotecas deste projeto são:

- React (mas preact-compat é usado para obter um pacote menor)
- React Apollo
- React Router
- Um pouco de lodash

## ROADMAP

É um primeiro rascunho, então muitas coisas ainda precisam ser feitas

 - Polir o estilo
 - Melhorar a possibilidade de classificação (até agora, está codificado por números de estrelas decrescentes).
 - Testes funcionais (porque sempre precisamos de testes :))
 - Como dito antes, um truque para obter uma maneira elegante de consultar apenas repositórios significativos que têm problemas.

Sinta-se à vontade para abrir PR ou enviar issues :)

## LICENÇA

MIT.
