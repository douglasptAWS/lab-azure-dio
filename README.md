# LAB AZURE
Repositório para armazenar resumo das lições aprendidas durante o desenvolvimento do lab "AZURE" na DIO.

- ***Aula 1:*** Criar conta na Microsoft Azure, efetuar o login e conhecer todos os recursos fornecidos.

## 🚀 Criando uma Máquina Virtual Windows no Portal do Azure

Este guia rápido ensina como criar uma máquina virtual (VM) do Windows Server 2022 no portal do Azure, ideal para fins educacionais e de teste.

### 🛠️ Etapas principais:

1. **Acessar o Portal do Azure**  
   Acesse: [https://portal.azure.com](https://portal.azure.com)

2. **Criar uma nova VM**
   - No menu lateral, selecione **Máquinas virtuais** e clique em **Criar** > **Máquina virtual do Azure**.
   - Preencha os detalhes:
     - **Nome da VM**: `myVM`
     - **Imagem**: `Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2`
     - **Nome de usuário**: `azureuser`
     - **Senha**: (defina uma senha segura)

3. **Configurar regras de porta de entrada**
   - Selecione **Permitir portas selecionadas**
   - Marque as opções:
     - **RDP (3389)**
     - **HTTP (80)**

4. **Revisar e criar**
   - Clique em **Examinar + criar**
   - Após a validação, clique em **Criar**

5. **Conectar-se à VM**
   - Após a implantação, vá para o recurso da VM
   - Clique em **Conectar** > **RDP** e baixe o arquivo `.rdp`
   - Conecte-se com as credenciais definidas anteriormente

6. **Instalar o servidor web IIS**
   - No PowerShell da VM, execute:

     ```powershell
     Install-WindowsFeature -name Web-Server -IncludeManagementTools
     ```

   - Acesse o IP público da VM no navegador para ver a página padrão do IIS

> ⚠️ **Nota**: Este procedimento é destinado a ambientes de aprendizado e testes, e não é recomendado para produção.

---

🔗 [Documentação completa no site oficial da Microsoft](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/quick-create-portal)

## 🗄️ Criando uma Instância Gerenciada de SQL do Azure via Portal

Este guia rápido ensina como criar uma Instância Gerenciada de SQL do Azure usando o portal do Azure, ideal para fins educacionais e de teste.

### 🛠️ Etapas principais:

1. **Acessar o Portal do Azure**  
   Acesse: [https://portal.azure.com](https://portal.azure.com)

2. **Iniciar a criação da instância**  
   - No menu esquerdo, selecione **SQL do Azure**.  
   - Se não estiver visível, clique em **Todos os serviços** e pesquise por "SQL do Azure".  
   - Clique em **+ Criar** para abrir a página de opções de implantação do SQL.  
   - No bloco **Instâncias gerenciadas de SQL**, clique em **Mostrar detalhes** e selecione **Instância única**.  
   - Clique em **Criar** para iniciar a configuração da instância.

3. **Configurar a instância (Guia Básico)**  
   Preencha as informações obrigatórias:
   - **Assinatura**: Selecione sua assinatura do Azure.
   - **Grupo de recursos**: Crie um novo ou selecione um existente.
   - **Nome da instância gerenciada**: Defina um nome válido.
   - **Região**: Escolha a região desejada para a instância.
   - **Pertence a um pool de instâncias?**: Selecione "Não" para criar uma instância única.
   - **Método de autenticação**: Escolha "Autenticação do SQL".
   - **Logon de administrador da instância gerenciada**: Defina um nome de usuário.
   - **Senha de administrador**: Defina uma senha segura.

4. **Configurar a rede (Guia Rede)**  
   - **Rede virtual**: Selecione uma existente ou crie uma nova.
   - **Sub-rede**: Escolha uma sub-rede dedicada para a instância.
   - **Grupo de segurança de rede**: Configure conforme necessário para controlar o tráfego de entrada e saída.

5. **Revisar e criar**  
   - Clique em **Revisar + criar**.
   - Após a validação, clique em **Criar** para iniciar a implantação da instância.

> ⚠️ **Nota**: A implantação de uma instância gerenciada é uma operação de longa duração. A primeira instância em uma sub-rede pode levar mais tempo para ser provisionada.

---

🔗 [Documentação completa no site oficial da Microsoft](https://learn.microsoft.com/pt-br/azure/azure-sql/managed-instance/instance-create-quickstart?view=azuresql&tabs=azure-portal)

## 🧩 Conceitos Fundamentais do Azure

### 📁 Grupo de Recursos (Resource Group)
Um **Grupo de Recursos** é um contêiner lógico que agrupa recursos relacionados do Azure, como VMs, bancos de dados, redes e mais. Ele facilita a organização, gerenciamento, monitoramento e controle de acesso aos recursos que compartilham o mesmo ciclo de vida.

- Exemplo: uma VM, um banco de dados e uma rede virtual podem estar no mesmo grupo de recursos chamado `MeuProjetoDev`.

---

### 📜 Log de Atividades (Activity Log)
O **Log de Atividades** fornece um histórico das operações realizadas na conta do Azure, como criação, modificação ou exclusão de recursos. É útil para auditoria, rastreamento de mudanças e solução de problemas.

- Exemplo: saber quem deletou uma máquina virtual e quando isso ocorreu.

---

### 👥 IAM (Identity and Access Management)
**IAM (Gerenciamento de Identidade e Acesso)** controla **quem pode acessar o quê** dentro do Azure. Com ele, você define **papéis (roles)** e **permissões** para usuários, grupos ou aplicações.

- Exemplo: dar permissão de “Leitor” para um usuário que só pode visualizar, mas não alterar os recursos.

---

### 🌐 Rede Virtual (Virtual Network - VNet)
A **Rede Virtual** é a fundação da infraestrutura de rede no Azure. Ela permite que recursos do Azure se comuniquem entre si com segurança, e também com redes locais via VPN ou ExpressRoute.

- Funciona como uma rede local na nuvem, com sub-redes, endereços IP, grupos de segurança e regras de roteamento.

---

### 📅 Eventos (Eventos e Alertas)
Os **Eventos** permitem acompanhar ações e mudanças nos recursos, podendo ser usados para configurar alertas automatizados. São úteis para **monitoramento proativo**, como falhas, picos de uso ou atividades não esperadas.

- Exemplo: criar um alerta para ser notificado por e-mail quando uma VM for desligada.
  
---

Esses conceitos são essenciais para administrar e monitorar recursos com eficiência dentro do Azure.


## 💻 Como Criar uma Máquina Virtual no Azure (via Portal)

Este passo a passo mostra como criar rapidamente uma **máquina virtual (VM)** no Azure com sistema operacional Windows.

### 🛠️ Etapas:

1. **Acessar o Portal do Azure**  
   - Link: [https://portal.azure.com](https://portal.azure.com)

2. **Navegar até Máquinas Virtuais**  
   - No menu esquerdo, clique em **"Máquinas virtuais"**  
   - Clique em **"+ Criar"** > **"Máquina virtual do Azure"**

3. **Preencher informações básicas**  
   - **Assinatura**: selecione a desejada  
   - **Grupo de recursos**: crie um novo ou selecione um existente  
   - **Nome da VM**: ex: `MinhaVMWindows`  
   - **Região**: escolha a mais próxima de você  
   - **Imagem**: selecione o sistema (ex: Windows Server 2022)  
   - **Usuário e senha**: defina credenciais para acesso RDP

4. **Configurar portas de acesso**  
   - Marque as portas que deseja liberar:  
     - **RDP (3389)** para acesso remoto  
     - **HTTP (80)** se for usar servidor web

5. **Revisar e Criar**  
   - Clique em **"Revisar + criar"**  
   - Após validação, clique em **"Criar"**

6. **Acessar a VM**  
   - Após a implantação, vá até o recurso da VM  
   - Clique em **"Conectar"** > **"RDP"**  
   - Baixe o arquivo `.rdp` e conecte-se com as credenciais definidas

---

### 💡 Dicas:
- Para testar um site, você pode instalar o IIS com o comando no PowerShell da VM:

  ```powershell
  Install-WindowsFeature -name Web-Server -IncludeManagementTools




