# Testes de API com Apache JMeter — Pets API

##  Sobre o projeto

Este repositório contém um plano de testes de API desenvolvido com **Apache JMeter 5.6.3**, utilizando uma API de Pets executada em ambiente local.

O projeto tem como objetivo praticar a configuração e execução de testes de carga e performance, utilizando diferentes modelos de geração de usuários virtuais, dados parametrizados e recursos de monitoramento.

## Objetivos

- Configurar e executar testes de API utilizando o Apache JMeter.
- Trabalhar com diferentes modelos de carga.
- Parametrizar dados de teste utilizando arquivos CSV.
- Realizar autenticação e utilizar tokens nas requisições.
- Monitorar transações por segundo e resultados das execuções.
- Gerar relatórios para análise de performance.

## Tecnologias e ferramentas

| Ferramenta | Utilização |
|---|---|
| Apache JMeter 5.6.3 | Criação e execução dos testes |
| Basic Graphs | Visualização de métricas |
| Throughput Shaping Timer | Controle da taxa de requisições |
| Custom Thread Groups | Configuração de modelos de carga |
| CSV Data Set Config | Parametrização de dados |
| JSON Extractor | Extração de informações das respostas |
| HTTP Header Manager | Configuração de cabeçalhos HTTP |

## 📁 Estrutura do projeto

```text
pets-api-jmeter-tests/
├── data/
│   └── pets_50_linhas.csv
├── pets-api-tests.jmx
├── README.md
└── .gitignore
```

**Descrição dos arquivos:**

- `pets-api-tests.jmx`: plano principal de testes do JMeter.
- `data/pets_50_linhas.csv`: massa de dados utilizada durante a execução.
- `README.md`: documentação do projeto.
- `.gitignore`: configuração dos arquivos que não devem ser versionados.

## Cenários de teste

O plano contempla requisições para diferentes operações da API de Pets.

| Método | Endpoint | Objetivo |
|---|---|---|
| POST | `/login` | Autenticar e obter token |
| GET | `/users` | Consultar usuários |
| POST | `/pets` | Cadastrar pets |
| GET | `/pets` | Consultar pets |

O projeto também utiliza diferentes configurações de execução, incluindo Thread Groups e recursos de controle de throughput.

## Como executar

### 1. Pré-requisitos

- Apache JMeter 5.6.3 instalado.
- Plugins Basic Graphs, Throughput Shaping Timer e Custom Thread Groups.
- API de Pets executando localmente.
- Java compatível com a versão do JMeter.

### 2. Clonar o repositório

```bash
git clone https://github.com/SEU_USUARIO/pets-api-jmeter-tests.git
cd pets-api-jmeter-tests
```

Substitua `SEU_USUARIO` pelo seu usuário do GitHub.

### 3. Configurar o ambiente

Inicie a API de Pets em `localhost`, utilizando a porta configurada no plano de testes.

Verifique também se o arquivo `data/pets_50_linhas.csv` está disponível e se o caminho configurado no CSV Data Set Config está correto.

### 4. Executar os testes

Para abrir o plano na interface gráfica:

```bash
jmeter -t pets-api-tests.jmx
```

Caso o comando `jmeter` não esteja disponível no PATH, utilize o executável `bin/jmeter` da instalação.

Para executar o plano em modo não gráfico:

```bash
jmeter -n -t pets-api-tests.jmx -l results/test-results.jtl
```

Crie a pasta `results/` antes da execução.

## Relatórios e métricas

O projeto utiliza recursos do JMeter para acompanhar o comportamento das requisições durante os testes.

Entre as informações que podem ser analisadas estão:

- **Transactions per Second:** quantidade de transações processadas por segundo.
- **Throughput:** taxa de processamento das requisições.
- **Response Time:** tempo de resposta das operações.
- **Error Rate:** percentual de requisições com falha.
- **Summary Report:** resumo estatístico da execução.

### Gerar relatório HTML

Após executar os testes e gerar o arquivo `.jtl`, é possível criar um relatório HTML:

```bash
jmeter -g results/test-results.jtl -o reports/html
```

A pasta de destino do relatório deve estar vazia ou ainda não existir.

Os resultados de execução devem ser armazenados em `results/` e os relatórios gerados em `reports/`.

## Autenticação e segurança

O plano utiliza credenciais públicas de teste e realiza a autenticação para obter um token, utilizado nas requisições que exigem autorização.

Não devem ser publicados tokens reais, senhas privadas ou informações sensíveis.

## Aprendizados

Este projeto permite colocar em prática conhecimentos relacionados a:

- Testes de performance e carga.
- Configuração de cenários no Apache JMeter.
- Autenticação em APIs REST.
- Parametrização de dados de teste.
- Configuração de modelos de carga.
- Análise de métricas e relatórios.

## 👩‍💻 Autoria

Projeto desenvolvido para estudos e prática de testes de API e performance com Apache JMeter.
