# O que é Feature Store?

As primeiras implementações de Feature Stores vieram de empresas como Uber, Twitter e Spotify, onde modelos de ML e IA são centrais para o negócio. 

Em uma postagem de 2017 no blog de engenharia da Uber ([https://www.uber.com/en-BR/blog/michelangelo-machine-learning-platform/](https://www.uber.com/en-BR/blog/michelangelo-machine-learning-platform/)), é possível checar alguns relatos sobre o uso de Feature Store na plataforma de ML deles, o Michelangelo.

>  *... we added a layer of data management, a feature store that allows teams to share, discover, and use a highly curated set of features for their machine learning problems.  We found that many modeling problems at Uber use identical or similar features, and there is substantial value in enabling teams to share features between their own projects and for teams in different organizations to share features with each other.*

E ainda...

> *At the moment, we have approximately 10,000 features in Feature Store that are used to accelerate machine learning projects, and teams across the company are adding new ones all the time. Features in the Feature Store are automatically calculated and updated daily.*

Feature Stores podem operar como uma fábrica e/ou um repositório central de features para ML, onde dependendo da solução utilizada, é possível realizar gerenciando a coleta de dados brutos de várias fontes, realização de transformações, armazenamento, catalogação, versionamento, segurança, fornecimento e monitoramento de features, entre outras funcionalidades. 

O Feature Store é um recurso no sistema de ML que possibilita a automatização de processos reduzindo os esforços de engenharia através da criação de um catálogo compartilhado de features prontas para utilização pelos membros do time, permitindo a colaboração e compartilhamento de features entre equipes, com objetivo de acelerar a entrega de sistemas de ML. 

## Provedores de Feature Store

Hoje, existem múltiplas implementações comerciais e de código aberto. Idealmente soluções de Feature Stores avançadas devem oferecer todas as funcionalidade citadas aqui anteriormente. Comparar cuidadosamente as capacidades de diferentes provedores de Feature Stores é essencial, pois algumas soluções podem ter limitações, não fornecendo algumas funcionalidades que podem ser indispensáveis para o contexto do sistema de ML que está sendo desenvolvido. A seguir segue um comparativo de soluções atualmente disponíveis de Feature Store.

<div align="center">
  <table style="font-size: 10px; text-align: center; width: 100%;">
    <thead>
      <tr>
        <th style="padding: 5px; width: 12%;">Categoria</th>
        <th style="padding: 5px; width: 12%;">Feast</th>
        <th style="padding: 5px; width: 12%;">Tecton</th>
        <th style="padding: 5px; width: 12%;">MLRun</th>
        <th style="padding: 5px; width: 12%;">SageMaker</th>
        <th style="padding: 5px; width: 12%;">Vertex AI</th>
        <th style="padding: 5px; width: 12%;">Databricks</th>
        <th style="padding: 5px; width: 12%;">HopsWorks</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Código aberto</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Opção gerenciada</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">principais clouds</td>
        <td style="padding: 5px;">cloud + on-prem</td>
        <td style="padding: 5px;">na AWS</td>
        <td style="padding: 5px;">na GCP</td>
        <td style="padding: 5px;">principais clouds</td>
        <td style="padding: 5px;">cloud + on-prem</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Pipelines offline</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Pipelines em tempo real</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Recuperação de funcionalidades</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Motores de execução</td>
        <td style="padding: 5px;">Spark</td>
        <td style="padding: 5px;">Spark</td>
        <td style="padding: 5px;">Python, Dask, Spark, Nuclio</td>
        <td style="padding: 5px;">Nenhum</td>
        <td style="padding: 5px;">Spark</td>
        <td style="padding: 5px;">Spark</td>
        <td style="padding: 5px;">Spark, Flink</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Análise de funcionalidades</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Versionamento e linhagem</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Segurança das funcionalidades</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Monitoramento</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
      <tr>
        <td style="padding: 5px; white-space: nowrap;">Treinamento e serviço, integrado e automatizado</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Não</td>
        <td style="padding: 5px;">Sim</td>
      </tr>
    </tbody>
  </table>
</div>
<div align="center">
  <p style="font-size: 12px;">Fonte: <a href="https://www.oreilly.com/library/view/implementing-mlops-in/9781098136574/">Yaron Haviv, Noah Gift. Implementing MLOps in the Enterprise - A Production-First Approach. O'Reilly Media, Inc. 2023</a></p>
</div>

## Feature Store na Arquitetura do Sistema de ML

A figura a seguir ilustra a arquitetura ideal e membros do time que normalmente usam e interagem com um Feature Store. 

<div align="center">
  <figure>
    <img src="fs_ml_system.png" alt="Feature Store no sistema de ML">
    <figcaption style="font-size: 12px; font-weight: bold;">
      Fonte: <a href="https://www.oreilly.com/library/view/implementing-mlops-in/9781098136574/" style="font-size: 14px; font-weight: bold;">Yaron Haviv, Noah Gift. Implementing MLOps in the Enterprise - A Production-First Approach. O'Reilly Media, Inc. 2023</a>
    </figcaption>
  </figure>
</div>

> **IMPORTANTE!** Como já foi citado, nem todas as provedoras de Feature Store possuem as funcionalidades do desenho acima, o desenho ilustra uma arquitetura ideal de um serviço de Feature Store. 

Nesse sistema de ML, os dados brutos são ingeridos e transformados em features, que são catalogadas e servidas para diferentes aplicações (treinamento e inferência com modelo de ML), permitindo que Cientistas de Dados, Engenheiros de Dados e Engenheiros de ML/MLOps atualizem, recuperem, monitorem e utilizem as features.

A seguir são descritas as principais componentes de um Feature Store ideal:

1. **Camada de Transformação**: converte dados brutos offline ou online em features e as armazena tanto em um storage online (com chave/valor) quanto offline (objeto).

2. **Camada de Armazenamento**: armazena múltiplas versões de uma feature em tabelas de features (conjuntos de features) e gerencia o ciclo de vida dos dados (criação, adição, exclusão, monitoramento e segurança dos dados). A camada de dados armazena cada feature em duas formas: offline para treinamento e análise, e online para inferência e monitoramento.

3. **Recuperação de Features**: aceita solicitações para múltiplas features (vetores de features) e outras propriedades (como intervalos de tempo e dados de eventos), produzindo um snapshot de dados offline para treinamento ou um vetor em tempo real para inferência.

4. **Gerenciamento de Metadados e Catalogação**: armazena a definição de features, metadados, rótulos e relações.

Esses componentes trabalham em conjunto para proporcionar uma infraestrutura robusta que suporta todo o ciclo de vida de um sistema de ML, desde a ingestão de dados até a inferência em tempo real e o monitoramento contínuo.

## Data Warehouse X Feature Store

Embora um Data Warehouse tradicional e um Feature Store centralizarem dados de várias fontes para facilitar o acesso e uso para análise, eles têm objetivos distintos. Um Data Warehouse alimenta sistemas de Business Intelligence (BI) para suportar a tomada de decisões estratégicas, enquanto o Feature Store fornece dados processados para sistemas de Machine Learning (ML), como já foi comentado aqui. O Feature Store faz processamento repetitivo de dados, como normalização, limpeza e extração de features relevantes com engenharia de features, visando melhorar os modelos de ML existentes, colaborando com a automação de pipelines de ML, otimizando o desenvolvimento e a implantação de modelos de ML.

<div align="center">
  <figure>
    <img src="dw_versus_fs.png" alt="Data Warehouse X Feature Store">
    <figcaption style="font-size: 12px; font-weight: bold;">
      Fonte: <a href="https://paiml.com/docs/home/books/practical-mlops/" style="font-size: 14px; font-weight: bold;">Noah Gift, Alfredo Deza. Practical Mlops - Operationalizing Machine Learning Models. O'Reilly Media, Inc. 2021</a>
    </figcaption>
  </figure>
</div>
