# Bridge

## Contexto GeraL
Traduzido para ponte, a função brigde seria uma forma específica ou uma forma de estruturação de pasta em si com diferentes metáfora e conexões.

### Pastas Principais
Tal organização representa categorias principais de seus arquivos, tanto de dentro de uma empresa ou dentro de sua área de lazer: 
```bash
    Trabalho, Escola, Casa, e Jogos.
```

### Pastas secundárias
Agora que vc está com suas pastas principais criadas, ela precisaria de ter suas subpastas para cada categoria dentro de si:
```bash
    Trabalho:
    - Producao
    - Logística
    - Administração

    Escola:
    - Notas
    - Trabalhos
    - Tarefas

    Casa:
    - Alimentação
    - Compras
    - Contas

    Jogos:
    - Riot 
    - Epic Games
    - Steam
```

### Pastas de conexão(Brigde)
Essa Pasta a partir do momento que é criada e usada como tal função para conexoes entre pasta, facilita o acesso rápido do usuário e não e exigida o manuseio de pasta dentro de cada hierarquia.
```bash

    Trabalho:
        - Producao
        - Logística
        - Administração
            - ponte de recursos

        Escola:
        - Notas
        - Trabalhos
        - Tarefas
            - ponte de recursos

        Casa:
        - Alimentação
        - Compras
        - Contas
            - ponte de recursos

        Jogos:
        - Riot 
        - Epic Games
        - Steam
            - ponte de recursos
```

### Ideias adicionais
Sempre Mantenha suas pastas organizada com nomes consistentes e de faceis acessos para tais programas, assim sua navegação fica mais facilitada.Para tais nomenclaturas, adicione datas e números para tais arquivos, caso seus arquivos seja multiplo em interações e revisões.Sempre que possível revise e organize suas pastas conforme necessário, com o passar do tempo suas pastas precisarão de ajustes com eficiência. 

![](./Diagrama%20sem%20nome.drawio.png)


### Criação dos Objetos
```js
    const estruturaDePastas = {
  Trabalho: ["Producao", "Logistica", "Administracao"],
  Escola: ["Notas", "Trabalhos", "Tarefas"],
  Casa: ["Alimentacao", "Compras", "Contas"],
  Jogos: ["Riot", "EpicGames", "Steam"]
}; 
```

### Exemplo do caminho a ser percorrido pelo usuario
```js
const fs = require('fs');
const path = require('path');

// Função para criar estrutura de pastas
function criarEstruturaDePastas(estrutura, pastaPai) {
  for (const categoria in estrutura) {
    const subpastas = estrutura[categoria];
    const pastaCategoria = path.join(pastaPai, categoria);
    
    // Cria a pasta da categoria principal
    fs.mkdirSync(pastaCategoria);
    
    // Cria as subpastas dentro da categoria principal
    subpastas.forEach(subpasta => {
      fs.mkdirSync(path.join(pastaCategoria, subpasta));
    });
  }
}

// Caminho da pasta raiz
const pastaRaiz = "/caminho/para/sua/pasta/raiz";

// Chama a função para criar a estrutura de pastas
criarEstruturaDePastas(estruturaDePastas, pastaRaiz);
```

# Créditos: Erick S. / Camilla P.







