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

