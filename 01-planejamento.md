# Planejamento

## 1. Identificação do grupo

- **Disciplina:** Fundamentos de Redes de Computadores
- **Turma:** BSI 2026.2 (`bsi-26-2`)
- **Grupo:** 4
- **Projeto:** Rede virtualizada com 8 máquinas virtuais Ubuntu Server

### 1.1 Integrantes e usuários planejados

| Integrante | Usuário da VM |
|---|---|
| Lukas Gomes | `lukas.gomes` |
| Allysson Matheus | `allysson.matheus` |
| Abel Lucas | `abel.lucas` |
| Vitor Henrique | `vitor.henrique` |

## 2. Planejamento do endereçamento IPv4

A turma BSI 2026.2 utiliza a rede `192.168.26.0/24`, subdividida em sub-redes `/28`, sendo uma destinada a cada grupo.

O endereço de rede do Grupo 4 é determinado pela fórmula:

**192.168.26.(16 × X)/28**

Em que X representa o número do grupo.

Para o Grupo 4:

16 × 4 = 64

Portanto, a sub-rede utilizada será `192.168.26.64/28`.

### 2.1 Informações da sub-rede

| Parâmetro | Valor |
|---|---|
| Rede da turma | `192.168.26.0/24` |
| Sub-rede do Grupo 4 | `192.168.26.64/28` |
| Máscara de sub-rede | `255.255.255.240` |
| Endereço de rede | `192.168.26.64` |
| Primeiro endereço útil | `192.168.26.65` |
| Último endereço útil | `192.168.26.78` |
| Endereço de broadcast | `192.168.26.79` |
| Total de endereços | 16 |
| Endereços úteis | 14 |
| Endereços utilizados | 8 |
| Endereços disponíveis | 6 |
| Gateway | Não utilizado |

Uma sub-rede `/28` possui 16 endereços IPv4, sendo um reservado para identificar a rede e outro para broadcast.

Os 14 endereços restantes podem ser atribuídos a dispositivos.

O Grupo 4 utilizará os oito primeiros endereços úteis, de `192.168.26.65` até `192.168.26.72`.

Os endereços de `192.168.26.73` até `192.168.26.78` permanecerão livres.

## 3. Planejamento dos nomes e endereços das máquinas

O domínio definido para o Grupo 4 é:

`grupo4.bsi-26-2.maceio.lab`

Os hostnames seguirão o padrão:

`g4-pcY-vmZ`

Em que:

- `g4` identifica o Grupo 4.
- `pcY` identifica o computador físico, de 1 a 4.
- `vmZ` identifica a máquina virtual, 1 ou 2.

O FQDN (Fully Qualified Domain Name) será formado pelo hostname curto seguido do domínio do grupo.

### 3.1 Tabela de endereçamento e identificação das VMs

| VM | PC | Hostname | Interface / modo | IP / máscara | FQDN |
|---|---|---|---|---|---|
| VM1 | PC1 | `g4-pc1-vm1` | `enp0s3` · Bridge | `192.168.26.65/28` | `g4-pc1-vm1.grupo4.bsi-26-2.maceio.lab` |
| VM2 | PC1 | `g4-pc1-vm2` | `enp0s3` · Bridge | `192.168.26.66/28` | `g4-pc1-vm2.grupo4.bsi-26-2.maceio.lab` |
| VM3 | PC2 | `g4-pc2-vm1` | `enp0s3` · Bridge | `192.168.26.67/28` | `g4-pc2-vm1.grupo4.bsi-26-2.maceio.lab` |
| VM4 | PC2 | `g4-pc2-vm2` | `enp0s3` · Bridge | `192.168.26.68/28` | `g4-pc2-vm2.grupo4.bsi-26-2.maceio.lab` |
| VM5 | PC3 | `g4-pc3-vm1` | `enp0s3` · Bridge | `192.168.26.69/28` | `g4-pc3-vm1.grupo4.bsi-26-2.maceio.lab` |
| VM6 | PC3 | `g4-pc3-vm2` | `enp0s3` · Bridge | `192.168.26.70/28` | `g4-pc3-vm2.grupo4.bsi-26-2.maceio.lab` |
| VM7 | PC4 | `g4-pc4-vm1` | `enp0s3` · Bridge | `192.168.26.71/28` | `g4-pc4-vm1.grupo4.bsi-26-2.maceio.lab` |
| VM8 | PC4 | `g4-pc4-vm2` | `enp0s3` · Bridge | `192.168.26.72/28` | `g4-pc4-vm2.grupo4.bsi-26-2.maceio.lab` |

Todas as máquinas utilizarão a interface `enp0s3` em modo Placa em Ponte (Bridge), com endereçamento estático.

## 4. Bloco planejado do `/etc/hosts`

```text
# Grupo 4 - bsi-26-2 - grupo4.bsi-26-2.maceio.lab

192.168.26.65    g4-pc1-vm1.grupo4.bsi-26-2.maceio.lab    g4-pc1-vm1
192.168.26.66    g4-pc1-vm2.grupo4.bsi-26-2.maceio.lab    g4-pc1-vm2
192.168.26.67    g4-pc2-vm1.grupo4.bsi-26-2.maceio.lab    g4-pc2-vm1
192.168.26.68    g4-pc2-vm2.grupo4.bsi-26-2.maceio.lab    g4-pc2-vm2
192.168.26.69    g4-pc3-vm1.grupo4.bsi-26-2.maceio.lab    g4-pc3-vm1
192.168.26.70    g4-pc3-vm2.grupo4.bsi-26-2.maceio.lab    g4-pc3-vm2
192.168.26.71    g4-pc4-vm1.grupo4.bsi-26-2.maceio.lab    g4-pc4-vm1
192.168.26.72    g4-pc4-vm2.grupo4.bsi-26-2.maceio.lab    g4-pc4-vm2
```

## 5. Planejamento da topologia da rede

A topologia da rede representa a organização e a comunicação entre os equipamentos físicos e as máquinas virtuais do Grupo 4.

### 5.1 Topologia física

A topologia física será composta por quatro computadores do laboratório conectados a um switch.

Cada computador executará duas máquinas virtuais Ubuntu Server utilizando o VirtualBox.

| Computador físico | Máquinas virtuais |
|---|---|
| PC1 | `g4-pc1-vm1` e `g4-pc1-vm2` |
| PC2 | `g4-pc2-vm1` e `g4-pc2-vm2` |
| PC3 | `g4-pc3-vm1` e `g4-pc3-vm2` |
| PC4 | `g4-pc4-vm1` e `g4-pc4-vm2` |

As máquinas virtuais utilizarão o modo Bridge, permitindo sua conexão à rede física do laboratório através das interfaces dos computadores hospedeiros.

![Topologia física do Grupo 4](imagens/topologia-fisica-grupo4.png)

### 5.2 Topologia lógica

A topologia lógica representará as oito máquinas virtuais pertencentes à mesma sub-rede IPv4 `192.168.26.64/28`.

A comunicação entre as máquinas será realizada utilizando seus endereços IP, hostnames curtos ou FQDNs, com resolução de nomes por meio do arquivo `/etc/hosts`.

![Topologia lógica do Grupo 4](imagens/topologia-logica-grupo4.png)