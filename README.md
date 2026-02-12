<div align="center">
  <h1>🚀 Ender-5 Modernization Project</h1>
  <h3>MKS Eagle + Klipper + Pi Zero 2W</h3>
  
  <p>
    <img src="https://img.shields.io/badge/Printer-Ender--5-orange?style=for-the-badge" alt="Ender 5">
    <img src="https://img.shields.io/badge/Firmware-Klipper-blue?style=for-the-badge" alt="Klipper">
    <img src="https://img.shields.io/badge/Slicer-PrusaSlicer-brightgreen?style=for-the-badge" alt="PrusaSlicer">
  </p>
</div>

---

## 📝 Sobre o Projeto
Este repositório documenta o processo completo de atualização da **Creality Ender 5**, substituindo a eletrônica original pela placa **MKS Eagle** e utilizando o firmware **Klipper** gerenciado por um **Raspberry Pi Zero 2W**.

---

## 🛠️ Hardware Utilizado

<table align="center">
  <tr>
    <td width="50%">
      <ul>
        <li><b>Impressora:</b> Creality Ender 5 (Cartesiana)</li>
        <li><b>Placa-Mãe:</b> MKS Eagle V1.0 (MCU STM32F407) [cite: 1, 2]</li>
        <li><b>Host:</b> Raspberry Pi Zero 2W (USB)</li>
        <li><b>Drivers:</b> TMC2209 em modo UART </li>
      </ul>
    </td>
    <td width="50%">
      <ul>
        <li><b>Nivelamento:</b> Creality CR-Touch </li>
        <li><b>Resfriamento:</b> 2x Fans 24V (PB04010MS4) </li>
        <li><b>Alimentação Pi:</b> Fonte Externa (Futuro: Conversor Buck)</li>
        <li><b>Firmware:</b> Klipper [cite: 1, 2]</li>
      </ul>
    </td>
  </tr>
</table>

---

## 💠 Suporte de Hotend Customizado
Desenvolvi um modelo 3D exclusivo para acomodar o BL-Touch/CR-Touch e o sistema de refrigeração duplo.

<div align="center">
  <img src="https://fbi.cults3d.com/uploaders/14730752/illustration-file/bb92b031-b326-4e9c-ae47-717bdecdcb29/TampaEnder5-1.png" width="400" alt="Amart3D Shroud">
  <br>
  <a href="https://cults3d.com/:4028046">
    <img src="https://img.shields.io/badge/Download_no-Cults3D-red?style=for-the-badge&logo=cults3d" alt="Download Cults3D">
  </a>
</div>

* **Destaque:** Fluxo de ar otimizado para evitar *heatcreep* e melhorar saliências (*overhangs*).


---

## 🔧 Configuração do Firmware (MKS Eagle)
[cite_start]Configurações utilizadas no `make menuconfig` para a placa MKS Eagle[cite: 1, 3]:

* [cite_start]**Arquitetura:** STMicroelectronics STM32 [cite: 3]
* [cite_start]**Modelo:** STM32F407 [cite: 3]
* [cite_start]**Bootloader:** 48 KiB bootloader [cite: 3]
* [cite_start]**Interface:** USB (PA11/PA12) [cite: 3]

---

## ⚙️ Slicer & G-Code
Migração para o **PrusaSlicer 2.9.4**, otimizando a compatibilidade com Klipper.

* **Melhorias:**
    * Macros de `START_GCODE` para aquecimento inteligente.
    * Redução de *stringing* (encordoamento) em sistemas Bowden.
    * **Ajustes de Fluxo:** `max_extrude_cross_section: 6.0` para segurança em purgas densas.

---

## 📂 Estrutura do Projeto
* `📂 /klipper`: Arquivo `printer.cfg` otimizado.
* `📂 /firmware`: Instruções e arquivo `klipper.bin`.
* `📂 /3D_Models`: Arquivos para o suporte do Hotend.
* `📂 /slicer`: Perfis do PrusaSlicer.

---

<div align="center">
  <sub>Projeto desenvolvido por AmartManufatura.</sub>
</div>
