## Configurar o Azure Monitor para máquinas virtuais 

#### Parte 1

No portal, pesquise e selecione _Monitor_.
![Monitor](https://github.com/user-attachments/assets/ddc064ff-b57a-403c-8a94-8b2305dec709)

Apareceram vários recursos de insights, detecção, triagem e ferramentas de diagnóstico disponíveis.

Clique em _View_ na caixa **VM Insights** e selecione **Configure Insights**.
![Monitor VM INs](https://github.com/user-attachments/assets/5294d39f-0acc-4e41-aa37-e7939f4f25bf)

Selecione **Enable** ao lado da sua máquina virtual e depois clique em **Enable** na guia **Azure Monitor - Insights Onboarding**.
![MonitorEnbls](https://github.com/user-attachments/assets/de01b915-0028-46f7-97ae-4675f85ab80d)

Deixe tudo como está, depois selecione **Configure**.
![Monitor Cnfg INs](https://github.com/user-attachments/assets/09da1cf8-a794-42e8-8890-31beff258f8b)

#### Parte 2: Criar um alerta
Criando um alerta para quando uma máquina virtual for deletada.

Continue na página do _Monitor_, selecione **Alerts**.

Selecione **Create +** e depois _Alert rule_.

Marque a caixa da assinatura e selecione _Apply_.

Selecione a guia _Condition_ e depois clique no link _See all signals_.

Pesquise e selecione **Delete Virtual Machine** (Virtual Machines). Selecione _Apply_.

Na seção **Alert logic**, mantenha o padrão _All selected_.

Revise as seleções de Status. Mantenha o padrão _All selected_.

Deixe o painel Create an alert rule aberto para a próxima tarefa.

#### Parte 3: Configurar notificações do grupo de ações
Enviar notificação por e-mail para a equipe de operações.

Continue configurando seu alerta. Selecione **Use action groups** e depois **Create action group** no painel **Select action group**.

Na guia _Basics_, preencha os seguintes valores:

Selecione **Next: Notifications** e preencha:

Selecione _Email_, insira seu endereço de e-mail na caixa Email e clique em OK.

Selecione **Review + Create** e depois **Create**.

Após a criação do grupo de ações, vá para a guia **Next: Details** e preencha:

Selecione **Review + create** para validar, depois clique em **Create**.


#### Parte 4: Acionar um alerta e confirmar o funcionamento
Acionando o alerta e confirmando o recebimento da notificação.

No portal, pesquise e selecione _Virtual machines_.

Marque a caixa da VM machine-01-1.

Selecione _Delete_ na barra de menus.

Marque **Apply force delete**. Confirme no final da página que deseja excluir os recursos e clique em _Delete_.

No topo, clique no ícone de _Notifications_ e aguarde até que machine-01-1 seja excluída com sucesso.

Uum e-mail com o assunto Important notice: Azure Monitor alert VM was deleted was activated.... será enviado.

No menu lateral do portal do Azure, selecione _Monitor_ e depois _Alerts_.

Você deve ver três alertas detalhados gerados pela exclusão de machine-01-1.
