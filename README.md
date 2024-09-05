# Sysmk - Sistema de Relatórios Automáticos para Antenas Mikrotik

## Visão Geral

O **Sysmk** foi desenvolvido para gerar relatórios automáticos de redes Mikrotik ponto a ponto e multiponto. Ele coleta e compila as informações mais cruciais dos equipamentos via rádio, tais como:

- **SSID** (Nome da Rede)
- **IP**
- **Frequência**
- **Modo de Operação**
- **Largura de Banda**
- **Canal**
- **Protocolo**
- **Nome dos clientes conectodo em cada Multiponto**
- **Endereço Mac das antenas conectadas**
- **Sinal dos clientes**

O sistema opera de forma automática na rede, escaneando e coletando dados periodicamente de antenas Ponto a Ponto e MultiPonto. Uma vez configurado, ele executa o scan da rede de acordo com as datas e horários especificados, com a opção de realizar até dois scans por mês. Após cada scan, um relatório em formato **XLSX** é gerado automaticamente, contendo todas as informações relevantes em uma tabela estruturada.

## Funcionalidades

- **Configuração Automática**: Configure uma vez para que o sistema opere de forma contínua e automática.
- **Agendamento de Scans**: Escolha a frequência dos scans, com a opção de realizar até dois scans por mês.
- **Relatórios XLSX**: Geração automática de relatórios detalhados em formato XLSX após cada scan.
- **Gerenciamento de Usuários**: Possibilidade de cadastrar usuários de acesso leitura, utilizando o grupo de suporte.
- **Licenciamento**: O sistema requer uma assinatura ativa para liberar todas as funcionalidades, contribuindo para a manutenção e desenvolvimento do projeto.

## Requisitos

- **Sistema Operacional**: Ubuntu Server 24.04 LTS

## Instalação

Siga os passos abaixo para instalar o Sysmk:

### 1. Atualize o Sistema

```bash
sudo apt update && sudo apt upgrade -y && sudo apt dist-upgrade -y
```

### 2. Verificar fuso horário atual

```bash
# Verificar fuso horário atual
$ timedatectl

# Listar todos os fusos horários disponíveis
$ timedatectl list-timezones

# Defina o fuso horário da sua região
$ sudo timedatectl set-timezone America/Sao_Paulo

# Verificar se a alteração foi aplicada
$ timedatectl

# Habilitar sincronização com NTP
$ sudo timedatectl set-ntp true
```
### 3. Download e permisões

```bash
# Faça o Download do pacote
$ wget https://raw.githubusercontent.com/MXCodemax/Auto-Report/main/Sysmk-v1.0.0.tar.gz

# Extraia os arquivos com o comando seguinte
$ tar -xzvf Auto-Report-System-v1.0.0.tar.gz

# Acessar diretório dos arquivos
$ cd Sysmk-Auto-Report/automation

# Modificar arquivo Settings
$ nano autoreport/settings.py
ALLOWED_HOSTS = ['Seu IP Local']

# Permissão de execução
$ sudo chmod +x setup

# Execute o arquivo de instalação
$ ./setup
```
## Uso

### Acesso ao Sistema

Se a instalação foi concluída com sucesso:

1. **Acesse o sistema**: Abra um navegador e vá para o IP da máquina onde o sistema está instalado.
   
2. **Faça login**: Use as credenciais fornecidas ou configuradas durante a instalação para acessar o sistema.

3. **Cadastro dos Blocos de IP**: Após o login, faça o cadastro dos blocos de IP a serem scaneados. Isso é necessário para que o sistema saiba quais intervalos de IP deve monitorar durante os scans.

### Acesso de Usuários

Administre os acessos ao sistema cadastrando usuários com permissões específicas. É possível configurar permissões como leitura para o grupo de suporte, garantindo que os usuários tenham acesso adequado às funcionalidades do sistema.

### Geração de Relatórios

O sistema gera automaticamente um arquivo **XLSX** formatado como uma tabela após a conclusão de cada scan. Os relatórios são armazenados no diretório configurado e podem ser acessados para análise posterior.

## Licenciamento

O **Sysmk** requer uma assinatura ativa para desbloquear todas as suas funcionalidades. A assinatura:

- **Permite o uso completo do sistema**.
- **Ajuda a manter e desenvolver o projeto**.
- **Inclui suporte técnico e atualizações regulares**.

## Suporte

Para suporte técnico ou dúvidas relacionadas ao sistema, entre em contato através dos canais de suporte especificados na sua assinatura.
