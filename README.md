# Ender-5-MKS-Eagle-Klipper-Pi-Zero-2W
Este repositório documenta o processo completo de atualização da Creality Ender 5, substituindo a eletrônica original pela placa MKS Eagle e utilizando o firmware Klipper gerenciado por um Raspberry Pi Zero 2W.

🛠️ Hardware Utilizado
  *Impressora: Creality Ender 5 (Cinemática Cartesiana).

  *Placa-Mãe: MKS Eagle V1.0 (MCU STM32F407).

  *Host: Raspberry Pi Zero 2W (Conectado via USB).

  *Firmware: Klipper.

  *Drivers de Motor: TMC2209 em modo UART.

  *Nivelamento: Creality CR-Touch.

  *Resfriamento da Peça: 2x Fans 24V (Modelo PB04010MS4) em portas independentes.

  *Alimentação do Pi: Temporariamente via fonte externa (Planejado: Upgrade para Conversor Buck 24V -> 5V).

📂 Estrutura do Projeto
  /klipper: Contém o arquivo printer.cfg otimizado.

  /firmware: Instruções de compilação e o arquivo klipper.bin.

  /3D_Models: Link e arquivos para o suporte do Hotend (Fans + BL-Touch).

  /slicer: Perfis do PrusaSlicer 2.9.4.

🔧 Configuração do Firmware (MKS Eagle)
Para compilar o firmware para esta placa, utilize as seguintes definições no make menuconfig:

  *Micro-controller Architecture: STMicroelectronics STM32

  *Processor model: STM32F407

  *Bootloader offset: 48KiB bootloader

  *Communication interface: USB (on PA11/PA12)

💠 Suporte de Hotend Customizado
Desenvolvi um modelo 3D exclusivo para acomodar o BL-Touch e o sistema de resfriamento duplo (2x Fans 24V).
<img width="1366" height="559" alt="TampaEnder5-1" src="https://github.com/user-attachments/assets/037cc329-a845-4dab-beff-a9e643ff02dc" />
<img width="1366" height="559" alt="TampaEnder5-3" src="https://github.com/user-attachments/assets/4d68d3e0-e740-4639-8253-5b7439166e9d" />
<img width="1366" height="559" alt="TampaEnder5-2" src="https://github.com/user-attachments/assets/e04e563c-76fa-4e11-89ab-0b11b39e008d" />
<img width="1366" height="559" alt="TampaEnder5-4" src="https://github.com/user-attachments/assets/9bc21d83-392d-4460-ba70-300e0e789939" />

Download: 
https://cults3d.com/en/3d-model/various/ender-5-dual-flow-shroud-mks-eagle-bl-touch-optimized-amartmanufatura-ed68

  Destaque: Fluxo de ar otimizado para evitar heatcreep e melhorar balanços (overhangs).

⚙️ Slicer & G-Code
  Migração do Creality Print para o PrusaSlicer 2.9.4, eliminando erros de compatibilidade (como o exclude_object fantasma).

  Inclusão de macros de START_GCODE para aquecimento inteligente e limpeza de bico.

  Perfis de filamento ajustados para redução de stringing em sistemas Bowden.
