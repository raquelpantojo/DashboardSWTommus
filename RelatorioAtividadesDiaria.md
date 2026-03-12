## 📋 Relatório de Atividades - Fevereiro 2026



### 🗓️ Semana 01 (02/02 a 06/02)



### 02-02-2026

* Dia de integração
* Reunião com o professor Adilton - definição de trabalho, levantamento de alguns requisitos necessários para aquisição das imagens



### 03-02-2026

* Reunião com o professor Adilton
* Pequenos testes de conexão da Telemed no phanton de mama
* Leitura da Dissertação da Vivian
* Leitura da Disser



#### 04-02-2026

* &#x20;Procurei com o Ricardo uma versão do SW em um computador do laboratório - encontramos uma versão que parece não ser a mais atualizada, mas usaremos esta como base



#### 05-02-2026 - Quinta

* Leitura da documentação do Usgfw2 SDK







#### 06-02-2026 - sexta

* 11h Reunião Tomus
* Leitura da documentação do Usgfw2 SDK
* Organização dos SDKs - entendi como usa-los
* C:\\Users\\raque\\Desktop\\ArtUs\_RFDataControl\\ArtUS-Manuals-and-SDK\\Development-Tools\\USGFW2-SDK-4.4.0\\SDK
* Deixei marcado com a Gabriela para conversarmos sobre Identidade visual do SW.
* Criei um GitHub para documentação e commits tomus\_interface

https://github.com/raquelpantojo/tomus\_Interface/tree/main/b\_mode



Melhorias no MainWindow.xaml:

* Implementei slider do TGC

 





## 🗓️ Semana 02 (09/02 a 13/02)

#### 09-02-2026 - Segunda



Melhorias no MainWindow.xaml ::



\[x] criação de um botão cadastro de pacientes para que no futuro acesse o banco de dados do HC

\[x] ajustar tamanho do DockPanel.Dock="Top" para que fique melhor alinhado

\[x] Reduzir caixas do controle da Probe

\[x] Alterar a língua para inglês do DockPanel.Dock="Top" de todos os campos

\[x] Deixar Settings e About com cor do layout

\[x] Corrigir desalinhamento do botão Start Scan

\[x] Criar o botão > STOP - ButtonStop

\[x] Criar o botão > PLAY ButtonPlayCine

\[x] Criar a funcionalidade do botão > SAVE CINE ButtonSaveCine - deve salvar em formato de vídeo



\[x] Criação de um README com os SDKs organizados

\[x] Criação de um .md para anotação da organização semanal.





\[x] Criação da tela SettingWindow.xaml -- básica por enquanto -- com mais funcionalidades -- implementação no menu setiing

\[x] Alteração do texto do botão Freeze para FROZEN

\[x] Remoção do LineDensity no MainWindow



\[x] Alinhamento com o Ricardo sobre o desenvolvimento







#### 10-02-2026 - Terça

Melhorias no MainWindow.xaml ::



\[x] Atualizei o README com os SDKs

\[x] Fiz reunião com Gabrielle para conversarmos sobre a Identidade visual



Cor

* amarelo #FFEB00
* azul #130435



Fontes:

Poppins

Extenda30Deca



\[x] Baixei as fontes online

\[x] Em Conversa com o Ricardo, ele me disse que os botões do TGC devem ficar em baixo da imagem 

&#x20;   usar o slider em outra direção (vertical) 



#### 11-02-2026 - Quarta

\[x] Create 3 files:

* FontFamily: Poppins and Extenda20Deca
* Images: Logo
* Styles



\[x] Create a GlobalStyles.xaml - com os estilos de botões e fonts

Como usar:



Style="{StaticResource ModernButtonStyle}"

fontFamily ="{StaticResource PoppinsFont}"

fontFamily ="{StaticResource ExtendaFont}"





Color  ="{StaticResource PrimaryColorYellow}"

Color  ="{StaticResource PrimaryColorBlue}"



Button = "{StaticResource ButtonStyle}"





Melhorias no LoginWindow.xaml ::

\[x] Adicionei o LOGO criado pela Gabrielle - achei melhor retira-lo no momento pq o nome vai ser alterado

\[x] Add FontFamily="{StaticResource ExtendaFont}"





Melhorias no MainWindow.xaml ::



\[x] Quando abrir na tela o SW não pode ser fixo ao ponto do usuário querer abrir outro código em cima

\[x] Dentro de <windown Topmost="False" > usei "False" pq com True, o Windows força essa janela a ficar na frente de todos os outros programas (Chrome, Pastas, Calculadora, etc.), o que pode ser bem irritante para o usuário.



Implementando o LoginWindow -- gerou erro de conexão com a TELEMED

Resolvendo erros:



    <Page Include="LoginWindow.xaml">

      <Generator>MSBuild:Compile</Generator>

      <SubType>Designer</SubType>

    </Page>





Erros

1>C:\\Program Files\\Microsoft Visual Studio\\18\\Professional\\MSBuild\\Current\\Bin\\amd64\\Microsoft.Common.CurrentVersion.targets(3082,5): warning MSB3305: processando referência COM "Usgfw2Lib" do caminho "C:\\WINDOWS\\SysWow64\\usgfw2.dll". O importador da biblioteca de tipos não pôde converter a assinatura para o associado 'tagUsgMixingBitmap.hdc'.

1>C:\\Program Files\\Microsoft Visual Studio\\18\\Professional\\MSBuild\\Current\\Bin\\amd64\\Microsoft.Common.CurrentVersion.targets(3082,5): warning MSB3305: processando referência COM "Usgfw2Lib" do caminho "C:\\WINDOWS\\SysWow64\\usgfw2.dll". O importador da biblioteca de tipos não pôde converter a assinatura para o associado 'tagUsgMixingBitmap.hBitmap'.

1>C:\\Program Files\\Microsoft Visual Studio\\18\\Professional\\MSBuild\\Current\\Bin\\amd64\\Microsoft.Common.CurrentVersion.targets(3082,5): warning MSB3305: processando referência COM "Usgfw2Lib" do caminho "C:\\WINDOWS\\SysWow64\\usgfw2.dll". O importador da biblioteca de tipos não pôde converter a assinatura para o associado '\_userBITMAP.pBuffer'.

1>C:\\Program Files\\Microsoft Visual Studio\\18\\Professional\\MSBuild\\Current\\Bin\\amd64\\Microsoft.Common.CurrentVersion.targets(3082,5): warning MSB3305: processando referência COM "Usgfw2Lib" do caminho "C:\\WINDOWS\\SysWow64\\usgfw2.dll". O importador da biblioteca de tipos não pôde converter a assinatura para o associado 'tagMIXBITMAP.bmBits'.



Como a solução está aberta no Visual Studio, você precisa fechar a solução primeiro. Em seguida, abra o arquivo b\_mode\\b\_mode.csproj em um editor de texto e localize a seção <COMReference Include="Usgfw2Lib">. Altere <EmbedInteropTypes>True</EmbedInteropTypes> para <EmbedInteropTypes>False</EmbedInteropTypes>.



<COMReference Include="Usgfw2Lib">

  <Guid>{9F73D9AE-FAE1-4C82-AA35-342A0AB173D8}</Guid>

  <VersionMajor>1</VersionMajor>

  <VersionMinor>0</VersionMinor>

  <Lcid>0</Lcid>

  <WrapperTool>tlbimp</WrapperTool>

  <Isolated>False</Isolated>

  <EmbedInteropTypes>False</EmbedInteropTypes>

</COMReference>







\[x] Deixar MainWindow com os GlobalStyles.xaml Retirar styles muito arbitrários







\--- Melhorias no cabeçalho \[2h]

\[x] Adicionar imagem de Logo Retirar a imagem que esta no momento

\[x] Acrescentar CPF do paciente

\[x] Adicionar data no cabeçalho

\[x] Botão Register Patient deixar dentro do Grid e deixar na cor de fonte preto







### 12-02-2026 - Quinta





\[x] Alteração do nome:TOMMUS



\--- melhorias Informações da PROBE \[2h]

\[x] Modificar a cor dos botões

\[x] Adicionar cor nos indicadores - branco

\[x] No Botão escrever Freeze ou inves de Frozen

\[x] No Salvar Preset melhorar Grid e botões



11h-12h - Reunião Tommus



Tratamento de erros:



<Compile Include="MainWindow.xaml.cs">

      <DependentUpon>MainWindow.xaml</DependentUpon>

      <SubType>Code</SubType>

    </Compile>





\--- melhorias no Tomography Control \[2h ]

\[ x] Melhorar botões --

Deixar nesse sequencia:

1.vertical moviment

2.rotacional moviment

3.liner moviment



\[x] Probe Name -- não esta aparecendo



Dica de ícones:

Anterior,\\u23F4 ou \\u2039,◀ ou ‹

Próximo,\\u23F5 ou \\u203A,▶ ou ›



\[x] No header Gain--

mudar os Botões: <Button Content="⏴"  e  <Button Content="⏵" no Header Gain, deve ser um slider, usar modelo de slider que já estou usando no projeto



### 

### 13-02-2026 - Sexta



\[x]  Patient registration system and custom storage paths



Salvamento do botão REGISTER PATIENT:

No botão registre paciente será que daria para salvar os dados do paciente incluindo a data em um txt? E tbm criar uma pasta com as imagens desse paciente, isso alterando para diferentes pacientes, melhor não deixar um nome fixo e valores fixos para cada campo do cabeçalho deixe tudo limpo e ai a pessoa insere o nome e o registro e faz o registro, tbm somente deixe fixo o nome do paciente, os demais campos podem ficar abertos e o usuário decide se vai mesmo preencher ou não



O Menu Settings deveria abrir um menu que teria uma opção de abrir uma imagem e também configurações, nas configurações abre uma nova tela de configurações, como um Windows w dentro dela uma das opções seria o salvamento , e assim terá uma opção do usuário informar qual pasta quer salvar. Nesse menu settings no futuro terá outras funcionalidades, deixe comentado nos lugar que posso adicionar outras funcionalidades para que no futuro seja mais fácil para eu adicionar



A implementação foi concluída com sucesso. O botão "REGISTER PATIENT" agora coleta os dados dos campos (nome do paciente é obrigatório), cria uma pasta com o nome do paciente (substituindo espaços por "\_") dentro de "Patients", salva os dados em um arquivo "patient\_info.txt" incluindo a data, e define o paciente atual. Os campos do cabeçalho foram limpos para entrada do usuário. Os salvamentos de imagem e cine agora verificam se um paciente foi registrado e salvam na pasta correspondente, com nomes de arquivo baseados na data/hora para evitar conflitos. A compilação foi bem-sucedida após remover eventos não implementados.





\[ x] Image Modo B maior - centralizado - maior

o WindowsFormsHost sera que da pra gerar uma imagem maior? do ultrassom como eu altero isso?





\[x] Tratamento de erro ao inicializar o SW

Erro ao inicializar Hardware não é possível converter o objeto COM do tipo System\_\_COM Objeto na interface USgfw2LibUsgCointrol esta operação falhou porque a cahamada da QueryInterface no omcportamento COM para a interface

Não a há suporte para esta interface (Excesçao de HReSULT?0x800004002 E\_Nointerface





\[x] Criar um botão que entra no modo Cine -- assim quando abre o modo cine no Status vira: Mode Cine --

\[x] Melhorar botões modo Cine- já fiz isso na Terça -- talvez tenha no Gemini -- tenho que procurar

\[x] adicionar botão de stop scan

\[x] Ao lado do STATUS na barra de cima da imagem deixar ao lado do STATUS a situação RUN ou FROZEN colorido - alterar cor, por exemplo deixar RUN escrito colorido

\[x]  Criar um botão para abrir uma pasta de um paciente que já foi cadastrado





WinForm não é possível gerar uma imagem maior que de 910, ela fica desconfigurada -- tentei forçar o SDK a gerar uma imagem maior, mas deu muito problemas1

<WindowsFormsHost x:Name="winforms\_host"

                                  Grid.Column="2"

                                  MinWidth="600" MinHeight="400"

                                  Margin="50,81,0,300"

                                  Width="910"

                                  HorizontalAlignment="Center"

                                  ChildChanged="winforms\_host\_ChildChanged"/>







Fazer teste - e gerar lista de coisas para fazer na segunda

\[x] Arrumar a função de Dinamyc Range que não esta rodando corretamente









\[x ] Corrigir erro: -- esse erro resolveu quando eu compilo com Debug x64

Erro ao inicializar Hardware não é possível converter o objeto COM do tipo System\_\_COM Objeto na interface USgfw2LibUsgCointrol esta operação falhou porque a cahamada da QueryInterface no omcportamento COM para a interface

Não a há suporte para esta interface (Excesçao de HReSULT?0x800004002 E\_Nointerface







## 🗓️ Semana 03 (18/02 a 20/02) - semana do carnaval

#### 16-02-2026 - feriado carnaval

\-- não trabalhei



#### 17-02-2026 - feriado carnaval

\-- não trabalhei



#### 18-02-2026 Quarta -- a partir das 12h

\[x] Implementação do Dynamic Range

\[x] Melhorar o preset ver a possibilidade de salvar os dados.

\[x] Criei um json com as informações do presets

\[x] O json do preset não deve excluir cada vez que abre o software, deve manter os antigos

\[x] Mostrar os presets salvos

\[x] Informar ao usuário se quer mesmo excluir o preset criado.

\[x] preparar uma pequena apresentação para mostrar na reunião de amanha -- não vai ter reunião essa semana

\[x] Tentativa de usar o canva para aumentar o tamanho da janela de imagem do winform







#### 19-02-2026 -- Quinta

* Hoje foquei em tentar melhorar a visualização da imagem de ultrassom.



\[x] Resolver erro no botão TGC - o problema era que como a imagem estava invertida 90º não estava alterando corretamente os ganhos nas regiões corretas



\[x] problemas com o posicionamento da imagem:

Adicionei eixo y e x na imagem \[ Width vs depth]



\[x] Encontrei o problema, nessa imagem, depth é o eixo x da imagem, e o width é o eixo y nas imagens convencionais os eixos são invertidos, mas aqui precisamos que depth seja x e width seja y dessa forma, quando eu modifico o controle Depth preciso modificar o depth de fato que seria o eixo x e não o eixo y. analise isso



\[x] Problemas de posicionamento da caixa que recebe a imagem de ultrassom e a própria imagem de ultrassom

Devem ficar sobrepostas para que não ocorra erros de deslocamento do eixo em relação a imagem

como a imagem esta descolada, dentro da caixa isso quer dizer que o eixo delimita por exemplo 20 mm mas como a imagem esta com um tamanho menor,

os eixos ficam demarcando errado



\[x] Ao invés de usar o canva, usei o Border:



<Canvas x:Name="ultrasoundCanvas"

       Grid.Row="1" Grid.Column="1"

       Background="Black"

       ClipToBounds="True">

    <WindowsFormsHost x:Name="winforms\_host"

                      Canvas.Left="0" Canvas.Top="0"

                      Width="{Binding ActualWidth, ElementName=ultrasoundCanvas}"

                      Height="{Binding ActualHeight, ElementName=ultrasoundCanvas}"

                      HorizontalAlignment="Center"

                      VerticalAlignment="Stretch"

                      MinWidth="200" MinHeight="200"

                      ChildChanged="winforms\_host\_ChildChanged"/>

</Canvas>







!-- Ultrasound image (Column 2 — fills remaining space) -->

 					<Border x:Name="ultrasoundCanvas"

 								Grid.Row="0" Grid.Column="2"

 								Background="{StaticResource BackgroundDark}"

 								ClipToBounds="True">

 						<WindowsFormsHost x:Name="winforms\_host"

 											  HorizontalAlignment="Stretch"

 											  VerticalAlignment="Stretch"

 											  ChildChanged="winforms\_host\_ChildChanged"/>

 					</Border>









#### 20-02-2026 -- Sexta 

\[x] Melhorar o top -- informações do paciente -- botões de salvamento



\[x] no cabeçallho com os dados do paciente preciso adicionar esses campos, Patient Information Patiente ID Patiente Name Age Date of birth Gender Nº SUS Doctor Name CRM Date exame - data do dia Tambem preciso que essas informações sejam salvas corretamente

\[x] Organize o cabecalho de forma que fique mais intuitivo para o usuário relaizar os processos de adicionar um paciente salvar. editar e excluir, deixe mais visual e com uma cara profissional tipico de softwares clinicos medicos

\[x] Patient data fields :: Faça o tratamento da informação do campos de data de aniversário, deixar em formato de data

\[x] use o "C:\\Users\\raque\\OneDrive\\Documentos\\GitHub\\tomus\_Interface\\ArtUsRF2.py" Usando o código @AArtUsRF2.py como modelo quero criar a caixa vermelha dentro da imagem de ultrassom, e a linha  RF\_line, = ax\[0].plot(XRFline,YRFline,'g--'); a linha verde é a linha central onde futuramente será adquirido um gráfico de RF





\[x] use o caminho para encontrar o código @AArtUsRF2.py  "C:\\Users\\raque\\OneDrive\\Documentos\\GitHub\\tomus\_Interface\\ArtUsRF2.py" use-o como modelo
criar os stacks Focal Depth \[mm] e Steering Angle \[deg] dentro do grid dos controles da probe no lado esquerdo além do StackPanel crie as funcionalidades de cada um deles





\[x] Modificar para iniciar o software no modo run rapidamente e depois ir para o modo freeze

\[x] Atualizar README - Adicionar informações sobre as pastas de Imagem/Font/Styles

\[x] adicionar salvamento do botão TGC nos presets

\[x] Implementar função de salvar modo Cine salvar em arquivo de vídeo\[pensar ainda em qual formato]

\[x] Ler Documentação sobre :: Tentar criar controle serial no painel do tomograpy controls para enviar comando para o ESP





\[x] Melhorar StatusBar (Bottom) - retirar o texto READY - adicionar uma função de mensagem aonde, o usuário possa acompanhar o que esta sendo realizado





## 🗓️ Semana 04 (23/02 a 27/02)

\[x] Implementar controles de formação de feixe (Focal Depth e Steering Angle)

\[x] Integrar via SDK Usgfw2Lib os ajustes de profundidade focal (mm) e ângulo de deflexão (deg).

\[x] Criar metodo FocusUpdateGUI() e SteeringAngleUpdateGUI()

\[x] Implementar no grid de controle da probe

\[x] Adicionar essas informações no salvamento do preset

\[x] Adicionar essas palavras na troca de idioma no resources.resx - create LabelFocus e LabelSteeringAngle



usando o ArtUsRF2.py implemente corretamente o steering angle de forma que a caixa vermelha e a linha verde pontilhada do RF tambem se alterem quando aplicado a inclinação do angulo.



\[x] no Setting:

>>  Ter a possibilidade da pessoa indicar qual pasta quer salvar os dados do paciente -- ok  

>>  Adicionar um botão para exportar a imagem de uma pessoa e um vídeo - ok 

>>  Criar um modulo para mensagens para ter a possibilidade de modificar o idioma.









## 🗓️ Semana 05 (02-03 a 06-03)



\[x] Adicionar um StatusService.cs que fara a gestão das mensagens na StatusBar

\[x] implementar chaves para serem utilizadas no resources.resx

\[x] deixar automático a alteração de idioma, para que o usuário possa modifica-lo



\[x] Automatizei uma auditoria de verificação para investigar as principais falhas do  

 foi criado um dashboard para verificar a as principais falhas do projeto até o momento.

file:///C:/Users/raque/OneDrive/Documentos/GitHub/tomus\_Interface/Documentation/Project\_Dashboard.html



\[x] inicio da implementação modo Doppler

\[x] Erro com o modo Doppler System.ArgumentException: 'Value does not fall within the expected range.'



Modo BPDI (ID:12): DISPONÍVEL

  Streams: 2

    Stream 0: Mode=1, ID=0

    Stream 1: Mode=11, ID=0

Modo BCFM (ID:9): DISPONÍVEL

  Streams: 2

    Stream 0: Mode=1, ID=0

    Stream 1: Mode=8, ID=0

Modo BDPDI (ID:15): DISPONÍVEL

  Streams: 2

    Stream 0: Mode=1, ID=0

    Stream 1: Mode=14, ID=0

Modo BPW (ID:7): DISPONÍVEL

  Streams: 2

    Stream 0: Mode=1, ID=0

    Stream 1: Mode=4, ID=0

## 

## 🗓️ Semana 06 09-02 a 13-02)

Implementação com os motores de movimento:

\[x] Implementação dos modos de movimento : Vertical, Linear e Rotacional
 
\[x] Criação de style somente para os botões de movimento < > vertical, linear, rotacional BtnMotion



\[x] modificar a escrita dos Controles da Tomo:

Linear Motion, Vertical Motion, Rotational motion

Motion Analysis



\[x] Arrumar Botão freeze/RUN - label não esta aparecendo

\[x] Adicionar os botões: salvar imagem, modo cine e gráfico de FH em cima da imagem de saída

\[x] Melhorar alinhamento do grid do Status e dos modos de aquisição



\[x] Substituir texto estático "Ready" por um Binder que exibe eventos do sistema (ex: "Gravando...", "Hardware Conectado").
Para adicionar a mensagem na barra do status, use:
StatusService.SetStatus(AppResources.SUACHAVELABEL)

\[ ] Se entrar no modoB deve desativar o modo doppler

\[ ] Arrumar erro no ViewModel os textos não estão aparecendo corretamente.

\[ ] Implemnetar Focal Depht



\[ ] Modificar Settering Angle

Quando Steering Angle ativado, a imagem deve estar com profundidade de 90mm


\[x] Alterar texto do status para cada um dos modos de aquisição
\[x] Deixar o painel de controle do Doppler ativado somente quando esta em modo doppler


\[ ] Controles do Doppler, deve ter:

[x] PRF -- ok 

[x] Gain

[x] Power


Doppler window 12-03 e 13-03

Line Density 16-03

Frame Averaging 17-03

Wall Filter 18-03

B/Color Priority 19-03

Color Threshold 20-03

Baseline 20-03

------------------------------------------------------------------------------------
Movimento do Doppler Windows
o usuário terá três níveis de interação formas com o visualizador da caixa do doppler
1. Tamanho pré-definido 
Quando o doppler é ativado, o usuário pode selecionar caixa >> no painel do Doppler Control: "Small", "Medium" ou "Large".

>> Define uma base rápida. 
>> Útil quando o usuário quer resetar a janela para um tamanho padrão no centro da imagem sem precisar ajustar manualmente.

2. Movimento dos botões via direção (direito, esquerdo, cima e baixo)
PreviewMouseDown, PreviewMouseUp
Usei o DispatcherTimer para ter um movimento contínuo quando o botão estiver pressionado 

3. Interação Direta com o Mouse, Arrastar e redimensionar
Clicar no centro, arrasta livremente a janela nas posições X e Y
E clicando nas bordas para redimensionar livremente a largura e altura  


------------------------------------------------------------------------------------



próximas tarefas

Finalizar arquivo de relatório

desativar modo Doppler quando estiver outros modos ativos





Finalizar implementação do Doppler

Melhorar Layout central - depois de finalizar modo doppler









\[ ] Implementar Função modo Cine e verificar qual melhor formato para realizar o salvamento

\[ ] Melhorar StatusBar (Bottom) - retirar o texto READY - adicionar uma função de mensagem aonde, o usuário possa acompanhar o que esta sendo realizado

\[ ] Criação de um arquivo Log - para obter informações de acesso e problemas decorrentes

\[ ] add icon tommus no executável

\[ ] Criar um modulo para mensagens Resources.resx para melhorar o idioma



queria indicar a posição do transdutor, como convencialmente as pessoas utilizam a imagem de cima para baixo, no nosso caso usamos a imagem com o width no eixo y e o depth no eixo x teria como fazer uma indicação com uma imagem ou icone do transtudor de ultrassom mosrando que a imagem esta horizontal







## To-Do:


Implementar nos controles da probe a opção de selecionar qual dos transdutores estão sendo utilizados no momento 



Ideias futuras, após um dado tempo que o transdutor não modificou seu frame ocorre o modo freeze



\[ ] Na aba de baixo, retirar o READY - adicionar uma função de mensagem aonde, o usuário possa acompanhar o que esta sendo observado.

\[ ] criação de um arquivo Log - para obter informações de acesso e problemas decorrentes

\[ ] add icon tommus

\[ ] Add regex validation for special characters in patient names and CPF

\[ ] Alterar o nome de b\_mode para tommusImageSystem




Planejamento 
12-03 e 13-03 - implementação Doppler window 

----
Seg 16-03
>> Aula
>> Line Density 

Terça 17-03
>> Aula
>> Frame Averaging 

Quarta 18-03
>> Wall Filter 

Quinta 19-03
>> B/Color Priority 

Sexta 20-03
>> Color Threshold 
>> Baseline

---- 

Seg 23-03
Modo de visualização do Modo-B - View

Terça 24-03
Modo A

Quarta 25-03
Modo M

Quinta 26-03
Grafico de RF

Sexta 27-03
- Arrumar o eixo de Depth
- Vi que o Width esta indicando valores negativos de cima, indicação errada
---

---
Adicionar botão vermelho para STOP
