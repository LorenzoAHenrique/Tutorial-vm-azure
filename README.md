# Guia Rápido Azure — Criar VM e VMSS

Passo a passo básico para criar uma **Máquina Virtual (VM)** e um **Conjunto de Dimensionamento (VMSS)**.

---

## ✅ Pré-requisitos

- Conta no Azure (plano Azure for Students serve).  
- Acesso ao portal: [https://portal.azure.com](https://portal.azure.com)  

---

## 1️⃣ Criar uma Máquina Virtual (VM)

1. No portal: **Máquinas virtuais → Criar → Máquina virtual**  
2. Preencha os campos básicos:
   - **Assinatura:** Azure for Students  (Foi o que funcionou para mim)
   - **Grupo de recursos:** VMTest1 (clique em Criar novo)  
   - **Nome da VM:** VM-Azure-TESTE  
   - **Região:** South Africa North  
   - **Imagem:** Ubuntu Server 24.04 LTS – Gen2  
   - **Tamanho:** Standard B2s (ou similar)  
   - **Autenticação:** Chave SSH (crie ou use existente)  
3. Clique **Avançar → Discos** e mantenha o padrão (Standard SSD).  
4. Clique **Avançar → Rede** e deixe o IP público habilitado.  
5. Clique **Avançar → Monitoramento/Avançado** e mantenha padrões.  
6. Clique **Revisar + criar → Criar**.  

## 2️⃣ Criar um VM Scale Set (VMSS)

1. No portal: **Máquinas virtuais → Criar → Conjunto de Dimensionamento de Máquinas Virtuais (VMSS)**  
2. Preencha os campos básicos:
   - **Assinatura:** Azure for Students  
   - **Grupo de recursos:** VMTestes (crie se não existir)  
   - **Nome do VMSS:** VMTestes  
   - **Região:** East US  
   - **Modo de orquestração:** Flexível  
   - **Zona de disponibilidade:** Nenhuma  
   - **Imagem:** Ubuntu Server 24.04 LTS – Gen2  
   - **Tamanho:** Standard D2 v3 (2 vCPUs, ~8 GiB) ou similar  
   - **Autenticação:** Chave pública SSH (reutilize a chave da VM)  
3. Dimensionamento:
   - **Modo de dimensionamento:** Atualizar manualmente  
   - **Contagem inicial de instâncias:** 1  
4. Rede: mantenha as opções padrão (VNet, NIC, Balanceador).  
5. Clique **Revisar + criar → Criar**.

---

## 3️⃣ Limpeza (evitar custos)

Para não gerar cobranças indesejadas:

- Exclua a **Máquina Virtual (VM)**, o **IP público** e o **disco** associados.  
- Exclua o **VM Scale Set (VMSS)**.  
- Exclua os **Resource Groups** usados (**VMTest1** e **VMTestes**) para remover todos os recursos de uma vez.
