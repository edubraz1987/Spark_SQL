#### Extras:
  - Descrever qual estratégia você usaria para ingerir estes dados de forma incremental caso precise capturar esses dados a cada mes?

    > Continuaria usando o Spark e criaria um schedule orquestrada para ingerir automaticamente numa delta table ou em algum sistema de arquivos na cloud (para manter a disponibilidade) que aceite o particionamento, como o Hadoop, Hive ou o S3 da Amazon, sendo consumidos via API, dando prioridade para uma plataforma com suporte a SQL, já que sua migração, caso seja necessário um dia, se torna menos custosa.


  - Justifique em cada etapa sobre a escalabilidade da tecnologia utilizada.
    
    > Considerando a possibilidade exponencial de crescimento dos dados, após a normalização dos dados inseridos, os mesmos foram armazenados em formato parquet para garantir velocidade de leitura e gravação incremental. Este formato é indicado para um processamento rápido, economia de espaço, suporte a quase todos os tipos de dados e particionamento dos dados.

    > Em um segundo momento, houve a conexão e a leitura dos dados da API. Usar uma API tem suas vantagens como não gastar espaço lógico no seu próprio armazenamento, dados atualizados e confiáveis, reutilização de dados e disponibilidade, sem contar a flexibilidade para o uso dos mesmo dados em diversas frentes.

    > E no final, SQL e Spark. Uma combinação quase melhor que arroz com feijão. Parecem ter sido feitos um para o outro, com quase 40 anos de diferença.
    Por ser uma linguagem estável há tanto tempo, o SQL se tornou uma linguagem universal para buscas em Bancos de dados. E seu uso não se restringe apenas aí.
    Uma ampla compatibilidade e desempenho aprimorado em diversas plataformas e ambientes de criação.
    Seguro, fácil, intuitivo, ele oferece integridade para as mais diversas aplicações. Possui ainda uma comunidade de apoio muito extensa e ativa.

    > É notório que as tecnologias citadas possuem muito em comum, mas o que pode ser destacado são:
        - Escalabilidade;
        - Desempenho;
        - Compatibilidade;
        - Eficiência na consulta;
        - Disponibilidade dos dados;
        - comunidade de apoio;
        - suporte a grandes volumes de dados;
        - integração entre sistemas;



  - Justifique as camadas utilizadas durante o processo de ingestão até a disponibilização dos dados.

    > 1º - coleta de dados e Armazenamento 
        - dados coletados de fontes externas e armazenados no seu estado bruto.

    > 2º - Processamento 
        - envolve a limpeza, normalização, enriquecimento, entre outros.

    > 3º - Estruturas
        - Momento em que os dados são organizados em tabelas, colunas e linhas, seguindo esquemas pré-definidos.

    > 4º - Segurança 
        - Momento da disponibilização dos dados para outros sistemas e / ou usuários, respeitando políticas de segurança e autorização para garantir que apenas pessoas autorizadas acessem.

    > 5º - Gerenciamento, Distribuição e Entrega
        - Momento de análise para o monitoramento do desempenho do sistema, gerenciamento de carga, escalabilidade e resolução de problemas.
        Se os dados precisam ser entregues a sistemas externos, aplicativos ou usuários, uma camada de distribuição e entrega é configurada para fornecer dados de forma eficiente e confiável.

    > 6º - Arquivamento 
        - Arquivamento ou retenção por razões de conformidade ou análise de longo prazo.
