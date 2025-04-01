
# Sistema de Gerenciamento de Dados de Atletas

Este projeto é um sistema de gerenciamento de dados de atletas, onde você pode inserir, remover, buscar e visualizar registros de atletas, além de carregar dados de um arquivo CSV. Ele utiliza arquivos binários para armazenamento de dados e realiza a inserção e organização de registros de forma eficiente, lidando com a divisão de blocos de armazenamento quando necessário.

## Funcionalidades

O sistema oferece as seguintes funcionalidades:

- **Inserção de Dados**:
  - Via arquivo CSV: Você pode carregar dados de um arquivo CSV contendo informações de atletas.
  - Via entrada padrão: Permite inserir manualmente as informações de um atleta.

- **Busca de Dado Específico**: Você pode buscar um registro de atleta pelo ID.

- **Remoção de Dado Específico**: Permite remover um atleta do sistema através de seu ID.

- **Visualizar Dados**: Exibe todos os dados armazenados no sistema, incluindo dados organizados em diferentes blocos.

## Estrutura dos Arquivos

O sistema armazena os dados dos atletas em arquivos binários. Cada arquivo binário (com extensão `.dat`) representa um bloco de registros de atletas. Cada bloco possui um cabeçalho que contém informações sobre a quantidade de registros e o próximo bloco (caso haja).

### Estrutura de cada bloco:

- **Cabeçalho**: Contém:
  - `quantidade`: Quantidade de registros no bloco.
  - `proximo`: Índice do próximo bloco (ou -1, se for o último).

- **Registro de Atleta**: Cada atleta possui os seguintes atributos:
  - `id`: ID único do atleta.
  - `nome`: Nome do atleta.
  - `sexo`: Sexo do atleta (M/F).
  - `idade`: Idade do atleta.
  - `altura`: Altura do atleta.
  - `peso`: Peso do atleta.
  - `time`: Nome do time do atleta.

### Arquivos de Dados

Os dados dos atletas são armazenados em arquivos binários (`.dat`) de acordo com a lógica de blocos de dados. Cada bloco pode conter até 50 registros, e quando um bloco está cheio, um novo bloco é criado automaticamente.

## Instruções de Uso

### Pré-requisitos

- Compilador C++ (por exemplo, `g++`).
- Arquivo CSV com dados de atletas (caso deseje importar dados via CSV).

### Compilação

1. Salve o código-fonte em um arquivo com extensão `.cpp`, por exemplo, `sistema_atletas.cpp`.
2. Compile o código usando um compilador C++:
   ```bash
   g++ sistema_atletas.cpp -o sistema_atletas
   ```

### Execução

Após compilar, execute o programa com o seguinte comando:

```bash
./sistema_atletas
```

O menu de opções será exibido, e você poderá escolher entre as funcionalidades disponíveis:

1. **Inserção de dados via arquivo texto**: Carregue os dados dos atletas de um arquivo CSV.
2. **Inserção de dados via entrada padrão**: Insira manualmente os dados de um novo atleta.
3. **Remoção de dado específico**: Remova um registro de atleta através do ID.
4. **Busca de dado específico**: Busque um atleta pelo ID.
5. **Visualizar dados**: Exiba todos os dados armazenados nos blocos de dados.

### Exemplo de arquivo CSV

O arquivo CSV deve ter o seguinte formato:

```csv
id,nome,sexo,idade,altura,peso,time
1,João Silva,M,25,180,75,Time A
2,Ana Souza,F,22,165,60,Time B
3,Carlos Lima,M,28,175,80,Time A
...
```

### Remoção de Dados

Ao remover um registro, o sistema irá solicitar a confirmação antes de excluir os dados.

### Visualização de Dados

A visualização mostrará todos os registros de atletas, organizados por blocos de dados.

## Considerações Finais

Este sistema pode ser útil para gerenciar dados de atletas de maneira eficiente, lidando com grandes volumes de registros ao utilizar arquivos binários e organização em blocos. O projeto é flexível e pode ser expandido para incluir novas funcionalidades conforme necessário.

## Equipe

- Fábio Damas Valim (202410372)
- Guilherme Lirio Miranda (202410367)
- Marcos Vinicius Pereira (202411098)
