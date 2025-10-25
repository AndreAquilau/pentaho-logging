# 🔄 Pipeline ETL – Integração de Dados de Cliente

Bem-vindo ao repositório de ETL para integração e transformação de dados de clientes utilizando o [Pentaho Data Integration (Kettle)](https://community.hitachivantara.com/s/article/downloads). Este projeto inclui orquestração de jobs, carregamento de dados, agregações e mecanismos de logging para suportar fluxos de dados robustos.

## 📁 Estrutura do Projeto

| Arquivo/Fonte                      | Descrição                                           |
|-----------------------------------|-----------------------------------------------------|
| `Carga_Cliente.ktr`               | Transformação para carga de dados de clientes       |
| `Carga_Dados.ktr`                 | Transformação para carga geral de dados             |
| `IntegracaoJob.kjb`               | Job principal que orquestra as transformações       |
| `Transformation_Init_Jobs.ktr`    | Inicialização dos jobs e controle de execução       |
| `Transformation Agregacoes.ktr`   | Lógica de agregações para relatórios ou análises    |
| `Transformation_Logging.ktr`      | Transformação de logging para auditoria             |
| `logging.db`                      | Banco de dados SQLite para armazenar logs           |
| `shared.xml`                      | Configurações compartilhadas (conexões, variáveis)  |
| `shared.xml.backup`              | Backup das configurações compartilhadas             |
| `sql_script.sql`                  | Script SQL para criação ou migração de banco        |
| `README.md`                       | Documentação do projeto                             |

## ⚙️ Visão Funcional

- **Habilitar/Desabilitar Fluxo**: A maioria das transformações possui lógica para ativar ou desativar fluxos com base em parâmetros.
- **Agregações**: Processamento de dados para relatórios e análises.
- **Logging**: Logs de execução são armazenados em `logging.db` para rastreabilidade.
- **Orquestração de Jobs**: `IntegracaoJob.kjb` coordena a execução das transformações na ordem correta.

## 🚀 Como Executar

### Pré-requisitos

- [Pentaho Data Integration (PDI)](https://sourceforge.net/projects/pentaho/)
- Java Runtime Environment (JRE)
- SQLite (opcional, para visualizar `logging.db`)

### Execução

1. Abra o Spoon e carregue o arquivo `IntegracaoJob.kjb`.
2. Verifique se o `shared.xml` está configurado corretamente com suas conexões de banco.
3. Execute o job e acompanhe o progresso pelo Spoon ou pelos logs.

### Logs

- Os logs são gravados em `logging.db` via `Transformation_Logging.ktr`.
- Você pode consultar o banco usando qualquer visualizador SQLite.

## 🧪 Notas de Desenvolvimento

- As transformações são modulares e podem ser executadas individualmente.
- Use parâmetros para controlar a execução de fluxos (ex.: ativar/desativar carga de cliente).
- Configurações compartilhadas estão em `shared.xml`, com backup em `shared.xml.backup`.
