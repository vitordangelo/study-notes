# Segurança de redes: Crie um firewall com pfSense e iptables

## Sobre o iptables

Tecnicamente, o iptables é apenas uma ferramenta que controla o módulo **netfilter**, que é um framework que já está embutido no kernel do Linux.
Esse framework trabalha relacionado à rede e dentro dele conseguimos fazer o que precisamos em termos de proteção, que é uma **filtragem de pacotes**, ou seja, trabalhando com o firewall.

### Main Features

- stateless packet filtering (IPv4 and IPv6)
- stateful packet filtering (IPv4 and IPv6)
- all kinds of network address and port translation, e.g. NAT/NAPT (IPv4 and IPv6)
- flexible and extensible infrastructure
- multiple layers of API's for 3rd party extensions
