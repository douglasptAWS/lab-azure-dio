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


