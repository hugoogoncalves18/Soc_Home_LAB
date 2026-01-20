# Soc_Home_LAB
Criação de um laboratório Soc para aprendizagem e melhoria de técnicas avançadas de proteção, monitorização e resolução de problemas

1. **Arquitetura básica**
Segmentação de rede para simular ambiente empresarial. Num ambiente de testes nunca misturamos ferramentas de segurança com máquinas de utilizadores

-WAN(Internet Externa)
-VLAN10-SOC - rede onde estão as ferramentas de defesa (Wazuh, TheHive, MISP, Cortex) esta é a rede mais protegida
-VLAN20-Cop - rede onde estão as máquinas vitimas (AD, File Server, win 10)
-VLAN30- DMZ - rese onde estão os serviços expostos (Web Server, Mail Server, Honeypots)
-SPAN - Interface para o Zeek escutar o tráfego que passa pela Firewall

VMs
-Wazuh
-TheHive + Elastic
-Win Server
-Windows 10
