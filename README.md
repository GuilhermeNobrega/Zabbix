Zabbix monitora processos em uma rede. Sua arquitetura funciona como:

- **Interface web** para visualização;
- Banco de dados Zabbix para armazenamento dos dados recebidos;
- **Servidor Zabbix** para execução, recebimento, encaminhamento e disponibilidade dos dados vindos;
- **Agentes Zabbix** servem para coletar informações relacionadas a hardware, como memória, CPU, tráfego de rede e, após isso, enviar dados para o servidor (transferência via TCP/IP).

**Proxy Zabbix**:
  - Serve como intermediário entre agentes Zabbix e o servidor Zabbix, podendo realizar:
    - Coletar dados de monitoramento de hosts (máquinas) e mandar para o servidor;
    - Pode armazenar dados locais, visando reduzir a carga no servidor principal e permitir o monitoramento mesmo que esteja offline.

**Benefícios**:
- Redução de carga no servidor principal: O proxy Zabbix pode aliviar a carga no servidor central, especialmente em grandes ambientes de monitoramento com muitos hosts e itens monitorados.
- Monitoramento distribuído: Em redes distribuídas, os proxies Zabbix podem ser implantados em locais remotos para monitorar localmente os dispositivos e enviar dados ao servidor central, economizando largura de banda de rede e reduzindo a latência.
- Resiliência: Os proxies podem armazenar dados localmente e enviá-los para o servidor principal quando estiverem disponíveis. Isso garante que os dados de monitoramento não sejam perdidos em caso de desconexão temporária do servidor ou interrupções na rede.

**Configuração**:
- Um proxy Zabbix é configurado para se conectar a um servidor Zabbix específico.
- Os agentes Zabbix são configurados para enviar dados de monitoramento para o proxy em vez do servidor central.
- O proxy, por sua vez, encaminha os dados recebidos para o servidor Zabbix.

**Monitoramento Independente**:
- Os proxies Zabbix podem executar monitoramento independente, permitindo que realizem a coleta de dados, processamento e geração de alertas mesmo se o servidor principal estiver inacessível.
- Eles têm sua própria interface de administração onde é possível configurar hosts monitorados, itens, triggers, entre outros.
