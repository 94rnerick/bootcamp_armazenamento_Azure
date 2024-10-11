# Bootcamp_armazenamento_Azure
Este repositório fala um pouco sobre o que aprendi durante o modulo Armazenamento na Azure do Bootcamp Microsoft Azure Essentials da Dio.

# Vou falar um pouco sobre os serviços de armazenamento da Azure

### Azure Blob Storage
- **Descrição**: Um serviço de armazenamento de objetos escalável para grandes quantidades de dados não estruturados, como arquivos, imagens, vídeos e backups.
- Armazenamento de arquivos, dados de backup, streaming de mídia.

### Azure Files
- **Descrição**: Serviço de compartilhamento de arquivos que permite que sistemas de arquivos sejam montados via SMB e NFS, acessível por múltiplas VMs.
-  Compartilhamento de arquivos entre VMs, montagens de arquivos em ambientes locais e na nuvem.

### Azure Queue Storage
- **Descrição**: Sistema de filas assíncronas usado para armazenar mensagens entre componentes distribuídos de uma aplicação.
- Processamento em lote, comunicação entre serviços distribuídos.

### Azure Table Storage
- **Descrição**: Serviço NoSQL para armazenar dados estruturados de chave-valor em grandes volumes.
-  Armazenamento de dados semi-estruturados, log de eventos, telemetria.

---

## Opções de Migração para o Azure

### Azure Migrate
- **Descrição**: Ferramenta que ajuda na avaliação e migração de servidores, bancos de dados, aplicativos e dados locais para o Azure.
  - Avaliação de compatibilidade
  - Migração de VMs, bancos de dados e aplicações

### Azure Data Box
- **Descrição**: Solução física de migração de dados, usada para transferir grandes volumes de dados para o Azure por meio de dispositivos de armazenamento fornecidos pela Microsoft.
  - Transferência de dados em escala Petabyte
  - Ideal para ambientes com baixa largura de banda de rede

---

### Camadas de Armazenamento
1. **Hot**: Para dados acessados frequentemente.
   - Dados em tempo real, aplicações críticas.
2. **Cool**: Para dados acessados menos frequentemente, mas ainda necessários com algum nível de regularidade.
   - Backup de curto prazo, dados arquivados recentemente.
3. **Archive**: Para dados raramente acessados, com um tempo maior de recuperação.
   - Backup de longo prazo, dados de conformidade.

### Opções de Redundância
1. **LRS (Locally Redundant Storage)**: Mantém 3 cópias dos dados em uma única região.
   - Dados que podem ser recriados facilmente e não exigem alta disponibilidade entre regiões.
   
2. **GRS (Geo-Redundant Storage)**: Armazena 6 cópias dos dados em duas regiões geograficamente distantes.
   - Dados críticos que precisam de replicação geográfica para recuperação de desastres.

3. **ZRS (Zone-Redundant Storage)**: Armazena 3 cópias dos dados em diferentes zonas de disponibilidade dentro da mesma região.
   - Aplicações que exigem alta disponibilidade dentro de uma única região.

4. **GZRS (Geo-Zone-Redundant Storage)**: replica os dados entre diferentes zonas de disponibilidade dentro de uma mesma região. 
 - Quando você precisa de alta disponibilidade e recuperação rápida de dados em caso de falha de zonas de disponibilidade ou de uma região inteira. 
- Quando é essencial evitar a perda de dados e garantir a integridade e consistência dos mesmos em qualquer cenário de falha.

##  Como Criar uma Conta de Armazenamento no Azure

   - No menu à esquerda, clique em "Criar um recurso".
   
   - Na barra de pesquisa, digite "Conta de Armazenamento" e selecione a opção.

   - **Nome da Conta**: Insira um nome exclusivo para sua conta.
   - **Região**: Escolha a região onde os dados serão armazenados.
   - **Tipo de Conta**: Selecione "General Purpose v2" para suporte completo às funcionalidades mais recentes.
   - **Camada de Desempenho**: Escolha entre Standard (armazenamento magnético) ou Premium (armazenamento SSD).
   - **Redundância**: Escolha entre LRS, GRS, ZRS ou GZRS, dependendo do seu requisito de disponibilidade.

 **Revisar e Criar**:
   - Revise as configurações e clique em "Criar" para provisionar a conta de armazenamento.

---

##  Opções de Gerenciamento de Dados

###  AZCopy
- **Descrição**: Ferramenta de linha de comando para copiar dados de ou para uma conta de armazenamento Azure.
  - Transferências eficientes de grandes volumes de dados.
  - Suporte para blobs, arquivos e tabelas.
- **Exemplo de Comando**:
  azcopy copy 'C:\local\data' 'https://<storage_account>.blob.core.windows.net/<container>' –recursive

###  Azure Storage Explorer
**Descrição:** Aplicação gráfica que permite gerenciar dados no Azure Storage de forma intuitiva.
- Suporte para criar, editar e deletar blobs, arquivos, filas e tabelas.
- Permite copiar dados entre contas de armazenamento e o ambiente local.
Como Utilizar:
Baixe e instale o Azure Storage Explorer.
- Conecte-se à sua conta de armazenamento usando as credenciais ou chaves de acesso.
- Gerencie containers de blob, compartilhamentos de arquivos e outras opções de armazenamento visualmente.


