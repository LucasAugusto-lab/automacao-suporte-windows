# Windows Support & Automation Toolbox

Uma ferramenta centralizada em lote (`.bat`) desenvolvida para analistas de TI e administradores de sistemas. O script automatiza rotinas críticas de suporte técnico, diagnóstico de redes, manutenção de hardware e otimização do sistema operacional Windows em ambientes corporativos.

## Funcionalidades Principais

O script conta com um menu interativo com 30 opções divididas em pilares fundamentais de infraestrutura:

* **Manutenção de Sistema:** Reparo de arquivos corrompidos (`SFC`), agendamento de verificação de disco (`CHKDSK`), limpeza automatizada de arquivos temporários (`%TEMP%`), reinicialização e limpeza do Spooler de Impressão, e gerenciamento do Windows Update.
* **Diagnóstico e Ferramentas de Rede:** Testes avançados de latência, varredura automatizada de portas comuns de infraestrutura, flush/registro de DNS e liberação/renovação de IP via `ipconfig`.
* **Segurança e Auditoria:** Elevação automática de privilégios para Administrador, gerenciamento do estado do Firewall do Windows, exibição de conexões ativas (`netstat`) correlacionadas com PID e gerenciamento de contas locais.
* **Backup e Resiliência:** Exportação automatizada de drivers ativos do sistema com organização de pastas por timestamp e criação de pontos de restauração via PowerShell.

## Diferenciais Técnicos Implementados

* **Auto-Elevação (UAC Bypass Admin):** O script valida se possui privilégios administrativos no boot e, caso não possua, invoca o PowerShell para solicitar a elevação automaticamente.
* **Sistema de Log Persistente:** Cada ação executada pelo usuário gera um log com carimbo de data/hora (`%DATE% %TIME%`) salvo no diretório temporário para auditoria de suporte.
* **Sanitização de Input:** Tratamento robusto contra entradas inválidas ou nulas no menu, evitando crashes acidentais ou loops infinitos.

## Como Utilizar

1. Faça o download do arquivo `Suporte.bat`.
2. Execute o arquivo (ele solicitará permissão de Administrador automaticamente).
3. Selecione a opção desejada no menu interativo (1 a 30).

## Tecnologias e Comandos Utilizados

* **Windows Batch Scripting**
* **PowerShell Integration** (Test-NetConnection, Checkpoint-Computer)
* **Network Utils** (ping, nslookup, netstat, netsh, ipconfig, arp)
* **System Utils** (sfc, chkdsk, pnputil, w32tm, winget)

---
*Desenvolvido para otimizar o tempo de resposta em chamados de infraestrutura e service desk.*
