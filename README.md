# Relatório de Implementação de Serviços AWS

**Data:** 02 de junho de 2026
**Empresa:** Abstergo Industries 
**Responsável:** Santiago Peixoto de Moais

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Santiago Peixoto de Moais. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos.

## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, serão descritas as etapas do projeto:

### Etapa 1: 
- **Nome da ferramenta:** Amazon S3 Intelligent-Tiering
- **Foco da ferramenta:** Otimização automática de custos de armazenamento de objetos.
- **Descrição de caso de uso:** Armazenamento de arquivos estáticos, relatórios gerados por painéis de Business Intelligence e documentos de histórico da empresa que possuem padrões de acesso desconhecidos. O serviço move automaticamente os dados não acessados há 30 dias para camadas de armazenamento mais baratas (Infrequent Access), eliminando gastos excessivos sem cobrar taxas de recuperação ou impactar a disponibilidade dos arquivos.

### Etapa 2: 
- **Nome da ferramenta:** Amazon EBS (Volumes HDD otimizados para throughput - st1)
- **Foco da ferramenta:** Redução de custos em armazenamento de blocos para cargas de trabalho de Big Data.
- **Descrição de caso de uso:** Substituição de volumes SSD (gp3/io2) mais caros por volumes st1 nos servidores EC2 dedicados ao processamento massivo de logs e ao *data warehouse* da empresa. Como essas operações exigem leitura contínua e sequencial (taxa de transferência) em vez de operações aleatórias rápidas (IOPS), o st1 entrega a performance necessária por uma fração do preço.

### Etapa 3: 
- **Nome da ferramenta:** AWS Lambda
- **Foco da ferramenta:** Computação *Serverless* (sem servidor) com faturamento por milissegundo.
- **Descrição de caso de uso:** Migração de automações, scripts em Python (como processadores de QR Code) e rotinas de extração de dados que antes exigiam uma instância EC2 rodando 24/7. Com o Lambda, o código é executado estritamente sob demanda. A Abstergo Industries deixa de pagar por tempo de ociosidade de servidores, pagando apenas pelo tempo exato em que o código está rodando.

## Conclusão
A implementação de ferramentas na empresa Abstergo Industries tem como esperado a redução drástica nos custos mensais de infraestrutura em nuvem e a modernização da arquitetura, o que aumentará a eficiência e a produtividade da empresa. Recomenda-se a continuidade da utilização das ferramentas implementadas e a busca por novas tecnologias que possam melhorar ainda mais os processos da empresa.

## Anexos
* Documento de Arquitetura de Transição (Exportado do Figma).
* Planilha de Estimativa de Economia Mensal (Gerada via *AWS Pricing Calculator*).
* Código-fonte das funções Lambda e automações (disponíveis neste repositório).
