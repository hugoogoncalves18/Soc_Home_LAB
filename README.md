# Soc_Home_LAB
Criação de um laboratório Soc para aprendizagem e melhoria de técnicas avançadas de proteção, monitorização e resolução de problemas.

1. **Arquitetura básica**
Segmentação de rede para simular ambiente empresarial. Num ambiente de testes nunca misturamos ferramentas de segurança com máquinas de utilizadores.

-WAN(Internet Externa).
-VLAN10-SOC - rede onde estão as ferramentas de defesa (Wazuh, TheHive, MISP, Cortex) esta é a rede mais protegida.
-VLAN20-Cop - rede onde estão as máquinas vitimas (AD, File Server, win 10).
-VLAN30- DMZ - rese onde estão os serviços expostos (Web Server, Mail Server, Honeypots).
-SPAN - Interface para o Zeek escutar o tráfego que passa pela Firewall.

VMs
-Wazuh.
-TheHive + Elastic.
-Win Server.
-Windows 10.


2. **Definir VLANs**
Vamos criar 3 redes isoladas, NAT(sem DHCP, o pfSense vai dar IPs)
-VLAN10-10.0.10.0/24
-VLAN20-10.0.20.0/24
-VLAN30-10.0.30.0/24

3. **Criação do pfSense**
Adicionamos 4 placas de redes virtuais
-NIC1: Bridge - Acesso á Internet externa
-NIC2: VLAN10_SOC
-NIC3: VLAN20_CORP
-NIC4: VLAN30_DMZ
