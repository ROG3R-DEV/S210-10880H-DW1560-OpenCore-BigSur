# S210-10980HK(10880H)-DW1830-OpenCore-Monterey, suporte Monterey, Ventura

## No momento, basicamente não há nada para melhorar, então atualizações futuras serão atualizações regulares, ou seja, atualizações OpenCore e Kext

# Perceber:
+ **Se você precisar baixar o pacote de atualização completo toda vez que atualizar o sistema no macOS 13 Ventrua, tente desativar temporariamente o BlueToolFixup.kext no Kexts e reinicie para atualizar. **
+ **Se você desativar o BlueToolFixup.kext e reiniciar, o bluetooth pode funcionar normalmente, então você pode deletar o kext do arquivo de configuração**
+ **Se o bluetooth funcionar normalmente após reiniciar depois de desabilitar BlueToolFixup.kext, tente desabilitar BrcmFirmwareData.kext e BrcmPatchRAM3.kext. Se o bluetooth ainda funcionar depois de desabilitar esses dois kexts, você pode remover completamente os drivers relacionados ao bluetooth. **
+ **Se o bluetooth não funcionar após a reinicialização após desabilitar o BlueToolFixup.kext, habilite este kext após a conclusão da atualização**

# 2021.12.16 Nota importante: Quando verifiquei o registro de energia hoje, descobri que ele acordaria a cada duas horas. O motivo do despertar parece ser [acordar para acesso à rede] e outra tarefa RTC (não tenho certeza se o A tarefa RTC é porque está ativada) Ativar para acesso à rede), portanto, você precisa desativar "despertar para acesso Ethernet", iniciar automaticamente após falha de energia e ativar a soneca no gerenciamento de energia.

# A placa de rede i211AT está atualmente livre de unidade sob o mais recente Ventura e Monterey, portanto, o driver [AppleIGB](https://github.com/donatengit/AppleIGB) é excluído e não é mais necessário atualizar para 210, apenas diretamente i211 (ou você pode tentar reflashing com o firmware da placa de rede i211 fornecido em efi).

Baseado na versão oficial do opencore0.8.9

+ 2023.02.15 atualização oc para a versão oficial 0.8.9, atualização kext para a mais recente
+ 2023.01.04 atualização oc para 0.8.8 versão oficial, atualização kext para a mais recente
+ 2022.12.07 atualização oc para a versão oficial 0.8.7, atualização kext para a mais recente
+ 2022.11.08 atualização oc para 0.8.6 versão oficial, atualização kext para a mais recente
+ 2022.10.07 Remova o driver AppleIGB do i211 e teste-o sob o último Monterey e Ventrua para evitar o driver
+ 2022.10.06 atualização oc para 0.8.5 versão oficial, atualização kext para a mais recente
+ 2022.09.17 Atualize o driver AppleIGB para corrigir o problema de que a placa de rede i211 não pode acessar a Internet no macOS Ventura; personalize novamente a porta de saída de vídeo
+ 2022.09.07 atualizar oc para 0.8.4 versão oficial, atualizar kext para versão oficial; re-personalizar porta USB
+ 2022.08.02 atualização oc para 0.8.3 versão oficial, atualização kext para versão oficial
+ 2022.07.26 Resolva o problema de que a placa de rede i211at não pode acessar a Internet no macOS Monterey
+ 2022.07.11 Atualização oc para a versão de desenvolvimento 0.8.3, atualize alguns kexts para a versão de desenvolvimento (agora suporta macOS Beta3)
+ 2022.07.07 Atualização oc para 0.8.2 versão oficial, atualização kext para versão oficial (esta versão não suporta a instalação do macOS13 beta3)
+ 2022.06.12 Atualização oc para 0.8.2 versão de desenvolvimento, atualização kext para versão de desenvolvimento
+ 2022.06.07 atualizar oc para 0.8.1, atualizar kext para o mais recente
+ 2022.03.08 atualizar oc para 0.7.9, atualizar kext para o mais recente
+ 2022.02.11 atualizar oc para 0.7.8, atualizar kext para o mais recente
+ 2022.01.11 atualização oc para 0.7.7, atualização kext para a mais recente
+ 2021.12.16 Corrigir o problema de ser acordado a cada 2 horas depois de dormir
+ 2021.12.07 atualização oc para 0.7.6, atualização kext para a mais recente
+ 2021.11.10 atualização oc para 0.7.5, atualização kext para a mais recente
+ 2021.10.07 Adicionar parâmetro -revsbvmm, atualização pode ser detectada em qualquer SecureBootModel; fechar SecureBootModel
+ 2021.10.02 Alterar algumas configurações
+ 2021.09.30 Altere o AAPL de PciRoot(0x0)/Pci(0x2,0x0), ig-platform-id para 0900A53E e personalize novamente o patch da placa gráfica para resolver o problema de nenhuma saída DP em Monterey Beta8 (beta7 e as versões abaixo não foram testadas)
+ 2021.09.24 Atualização oc para a versão de desenvolvimento 0.7.4, diz-se que resolve o problema de reiniciar quando o beta6 é atualizado para o beta7, você precisa usar a versão mais recente do OCC e mudar para a versão de desenvolvimento para editar (você também pode use a versão mais recente do OCAT)
+ 2021.09.07 atualização oc para 0.7.3, atualização kext para a mais recente, suporte AirPlay para Mac de macOS12 (testado))
+ 2021.08.19 A versão Monterey Beta é suportada e pode ser instalada e usada normalmente, mas há problemas de compatibilidade com alguns softwares e Monterey.
+ 2021.08.03 Atualização oc para 0.7.2, atualização kext para a mais recente, suporte AirPlay para Mac de macOS12 (não testado)
+ 2021.08.02 Adicione o driver HoRNDIS, você pode compartilhar a Internet através do Android USB
+ 2021.07.23 Corrigir problema de reinicialização
+ 2021.07.14 Re-personalize USBMap.kext; corrija o problema de que o áudio DP ou o áudio HDMI não são reconhecidos em um único monitor
+ 2021.07.06 atualizar oc para 0.7.1, atualizar kext para o mais recente
+ 2021.06.09 atualizar oc para 0.7.0, atualizar kext para o mais recente
+ 2021.05.06 atualização oc para 0.6.9, atualização kext para a mais recente
+ 2021.04.07 atualização oc para 0.6.8, atualização kext para a mais recente
+ 2021.03.02 atualizar oc para 0.6.7, atualizar kext para o mais recente
+ 2021.02.24 Corrigir a falha de energia repentina frequente após conectar um dispositivo ipad no macOS 11.2.1 (20D75)

---
 
### 1. Minha configuração
Modelo S210, i9 10980hk, 64G, display 4K (mini dp) + display 4K (hdmi 2.0), placa de som é alc235 (o chefe disse que era alc 233, mas a id0x10ec0235 da placa de som é a alc 235 real)

### 2. Condições de trabalho
Os seguintes são baseados no teste BigSur 11.4, Catalina não testou. Se você quiser usar o Catalina, é recomendável testar com o 10.15.7 mais recente. (Testado em 19.08.2021, Monterey pode ser instalado e usado normalmente.)

①, tudo normal:
DP, HDMI2.0 (DP único, HDMI único, DP+HDMI)
acordar do sono
gerenciamento de energia nativo
DW1830Bluetooth
placa de rede wireless DW1830
I219V (aquele perto do USB3.0 duplo na parte de trás)
I211AT (aquele na parte de trás perto do conector de alimentação)
USB (3.0, 2.0, tipo-c)
Voo de acompanhamento, revezamento, lançamento aéreo
Fone de ouvido, microfone, áudio DP/HDMI

### 3. Configurações do BIOS
Inicialização - Configuração CSM - Suporte CSM [Desativar]

### 4. Outros problemas
Preferências do Sistema - Economia de Energia Ative para acesso à rede, desmarque-o, caso contrário, ele será ativado após um tempo após o repouso
Preferências do sistema - Economia de energia Iniciar automaticamente após um ponto de interrupção, desmarque-o, isso é inútil no Black Apple
Preferências do sistema - Economia de energia precisa desmarcar Ativar Power Nap, caso contrário, pode travar após um longo período de suspensão
Ao inicializar, se o logotipo da Apple for esmagado, tente outro monitor. Meu próprio XV273K Shadow Knight, conectado à porta HDMI, é plano no primeiro estágio da inicialização e é normal após entrar no sistema. Meu monitor portátil está conectado ao mini dp e o logotipo do processo de inicialização está normal.
Se você achar que os 4 slots de memória exibidos em Sobre esta máquina - Memória não correspondem ao número de slots de memória do host pequeno, consulte as configurações de informações de memória personalizadas do OpenCore0.6.3 e superior

### 5. Descrição de circunstâncias especiais
Modelos S210, 10880H, a placa de som é alc 282, o driver da placa de som reltek deve ser instalado em win
O id mais próximo de alc 282 é 86, a placa de som tem som, mas o microfone fica mudo;
Ou escolha VoodooHDA em vez de AppleALC; há defeitos neste método: em vários monitores com alto-falantes, apenas um monitor pode produzir som e, ao acordar, todos os monitores não produzirão som, mas a interface do fone de ouvido está normal

### 6. Você pode instalar o arquivo de suporte do macos no Windows (você pode baixá-lo no menu "Operação" do assistente de conversão de inicialização e instalá-lo após entrar no Windows), para realizar a função de escolher iniciar o sistema no Windows semelhante ao White Apple. Observe que você precisa atualizar o bootcamp em c:\program files\apple software update após a instalação, caso contrário, o bootcamp reconhecerá erroneamente que todos os discos mac podem ser iniciados como macos. Após a instalação, alguns discos ficarão ocultos, consulte [Como resolver completamente o problema do disco D ou outros discos ocultos após o win10 ser ativado e adicionar uma nova letra de unidade sempre] (http://www.purplestone.cn/share/2361.html)
