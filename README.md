# Projeto FNRC 2026.2 — BSI | Grupo 4

Repositório destinado à documentação das atividades práticas da disciplina de **Fundamentos de Redes de Computadores (FNRC)**, do curso de **Bacharelado em Sistemas de Informação (BSI)**, semestre **2026.2**.

O projeto envolve a criação, configuração e validação de máquinas virtuais utilizando Ubuntu Server, com foco em configuração de redes, endereçamento IP, gerenciamento de usuários e comunicação entre máquinas.

## 👥 Integrantes

- Lukas Gomes da Silva
- Allysson Matheus Paulo Ferreira
- Abel Lucas Cavalcante de Melo
- Vitor Henrique Vasconcelos

## 📁 Estrutura do Repositório

```text
fnrc-2026.2-bsi-pf-grupo4/
├── README.md
├── 01-planejamento.md
├── 02-criacao-das-vms.md
├── 03-usuarios.md
├── 04-rede-netplan.md
├── 05-hostname-e-hosts.md
├── 06-testes.md
├── configs/
│   ├── hosts
│   └── netplan/
│       ├── g4-pc1-vm1.yaml
│       └── ... (um arquivo por VM)
├── validacao/
│   ├── validacao-g4-pc1-vm1.txt
│   └── ... (uma validação por VM)
└── imagens/
    ├── topologia-grupo4.png
    ├── pc1_virtualbox_bridge.png
    ├── g4-pc1-vm1_ip_addr.png
    └── ... (demais capturas)
```

## 📚 Documentação do Projeto

| Etapa | Descrição | Arquivo |
|---|---|---|
| 01 | Planejamento, endereçamento IP, nomes, usuários e topologia | [01-planejamento.md](01-planejamento.md) |
| 02 | Criação das VMs e instalação do Ubuntu Server | [02-criacao-das-vms.md](02-criacao-das-vms.md) |
| 03 | Criação dos usuários dos integrantes | [03-usuarios.md](03-usuarios.md) |
| 04 | Configuração da rede em modo Ponte e IP estático via Netplan | [04-rede-netplan.md](04-rede-netplan.md) |
| 05 | Configuração dos hostnames e do arquivo `/etc/hosts` | [05-hostname-e-hosts.md](05-hostname-e-hosts.md) |
| 06 | Testes de conectividade, SSH e resolução de nomes | [06-testes.md](06-testes.md) |

## ⚙️ Arquivos de Configuração

- [Arquivo hosts](configs/hosts) — Configuração de resolução de nomes utilizada nas 8 VMs.
- [Configurações Netplan](configs/netplan/) — Arquivos YAML responsáveis pela configuração de rede de cada VM.
- [Validações](validacao/) — Saídas dos scripts de validação executados nas máquinas virtuais.
- [Imagens](imagens/) — Capturas de tela utilizadas como evidências das configurações e testes.

## 🖥️ Ambiente Utilizado

- **Virtualização:** Oracle VirtualBox
- **Sistema operacional:** Ubuntu Server
- **Rede:** Adaptador em modo Ponte (Bridged Adapter)
- **Endereçamento:** IPv4 estático
- **Configuração de rede:** Netplan
- **Acesso remoto:** SSH

## 🎯 Objetivo

Implementar um ambiente virtualizado de rede, composto por **8 máquinas virtuais**, aplicando os conceitos de endereçamento IP, configuração de interfaces de rede, identificação de hosts, administração de usuários e testes de comunicação entre sistemas Linux.

---

**Grupo 4 — FNRC | BSI — 2026.2**
