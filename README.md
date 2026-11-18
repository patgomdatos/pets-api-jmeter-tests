# Testes JMeter da API de Pets

Plano de testes para a API de Pets local. O arquivo `pets-api-tests.jmx` usa os dados de `data/pets_50_linhas.csv`.

## Como abrir

1. Use o Apache JMeter 5.6.3 com os plugins Basic Graphs, Throughput Shaping Timer e Custom Thread Groups. A instalação usada para criar o plano já tem esses plugins.
2. Inicie a API de Pets em `localhost` na porta configurada no plano.
3. Na pasta do projeto, abra o JMeter com o comando abaixo. Se `jmeter` não estiver no `PATH`, use o executável `bin/jmeter` da sua instalação.

   ```sh
   jmeter -t pets-api-tests.jmx
   ```

O plano usa credenciais públicas de teste e obtém o token ao autenticar. Guarde os resultados de execução em `results/` e os relatórios gerados em `reports/`.
