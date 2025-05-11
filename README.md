# **HACKINTOSH MR9A-PRO | XEON 2690v3 | RX 6750XT**
Hackintosh feito seguindo o passo a passo do Gabriel Luchina.<br>
Utilizar o GenSMBIOS para gerar os seriais para conseguir utilizar a loja da apple e ter um comportamento original.
## **Configuração do Hardware**
- **Placa-mãe:** MR9A-PRO x99  
- **Processador:** Intel Xeon E5-2690v3  
- **Memória RAM:** 32GB DDR4  
- **Placa de Vídeo:** RX 6750 XT (suporte aos codecs da Apple e aceleração via GPU)  
- **Placa Wi-Fi & Bluetooth:** Intel AX210  
- **Armazenamento:** XrayDisk Pro NVME de 512GB  
- **Mapeamento das portas USB:** Realizado com USBMap  

## **Sistema Operacional**
Rodando macOS Sonoma 14.7.5 com suporte completo a gráficos e conectividade.

## **Configuração do OpenCore**
- **Versão do OpenCore:** 1.0.4  
- **Modelo de Mac escolhido:** MacPro7,1  
- **Ajustes personalizados na EFI:**  
  - **Desativado:** MSR Lock, Above 4G Decoding, Resize BAR, VT-d e Security Boot  
  - **SSDTs utilizadas:**  
    - SSDT-DMAR.aml  
    - SSDT-EC.aml  
    - SSDT-GPRW.aml  
    - SSDT-HPET.aml  
    - SSDT-PLUG.aml  
    - SSDT-RTCAWAC.aml  
    - SSDT-SBUS-MCHC.aml  
    - SSDT-UNC.aml  
    - SSDT-USB-Reset.aml  -> Remover caso as USBs já tiverem sido mapeadas
    - SSDT-USBX.aml  
  - **Boot-args:** `keepsyms=1 debug=0x100 npci=0x3000`  
  - **Quirks ativados:**  
    - AppleCpuPmCfgLock: **Desativado**  
    - AppleXcpmCfgLock: **Desativado**  
    - AppleXcpmExtraMsrs: **Ativado**  
    - DisableIoMapper: **Ativado**  
    - DisableLinkeditJettison: **Ativado**  
    - PanicNoKextDump: **Ativado**  
    - PowerTimeoutKernelPanic: **Ativado**  
    - XhciPortLimit: **Ativado**  -> Desativar caso as USBs já tiverem mapeadas

## **Kexts Utilizadas**
A configuração usa as seguintes kexts para garantir funcionalidade estável:
- **Wi-Fi & Bluetooth:** AirportItlwm.kext, BlueToolFixup.kext, IntelBluetoothFirmware.kext, IntelBTPatcher.kext  
- **Áudio:** AppleALC.kext  
- **Performance & Correções:** CpuTscSync.kext, FeatureUnlock.kext, Lilu.kext, NootRX.kext, RestrictEvents.kext  
- **Armazenamento:** NVMeFix.kext, RealtekRTL8111.kext  
- **Gestão de Energia e Sensores:** SMCProcessor.kext, SMCRadeonSensors.kext, SMCSuperIO.kext, VirtualSMC.kext  
- **USB:** USBMap.kext, USBWakeFixup.kext, XHCI-unsupported.kext  

## **Benchmarks**
Os testes de desempenho foram realizados com **Geekbench 6**:
- **Single-Core:** 888  
- **Multi-Core:** 6608
- **Gráficos:** 154663 (Metal)

## **Capturas de Tela**
Inclua imagens do sistema funcionando, mostrando:
- **Sobre Este Mac**
![A3BECD8E-3164-4304-B962-34D816F91AF7](https://github.com/user-attachments/assets/87a4c030-db7c-406c-a7c0-b6dd5e104e35)

- **Geekbench Scores** 
![58038F4C-9A8D-4059-8813-64045AD42C22](https://github.com/user-attachments/assets/58130c54-06ef-4e67-b7e3-998058226a02)
![46EF5D37-8640-4B48-9329-048D9A0F10BB](https://github.com/user-attachments/assets/4c8b34a4-5f0c-44c6-88df-731946a3897f)
 
- **Monitoramento de sensores (HWMonitorSMC, por exemplo)**

---

 
