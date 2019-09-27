# NRF52
NRF52832

- Updating Bootloader Error :
  If you get such error when you try to update bootloader with Arduino Ide ; 
    "Usage: adafruit-nrfutil.exe dfu serial [OPTIONS]
     Error: Invalid value for "-pkg" / "--package": Path "...bootloader/feather_nrf52832/feather_nrf52832_bootloader-0.2.13_s132_6.1.1.zip"      does not exist.
     Error while burning bootloader."
     
     
   You may try this solution with your own responsibility;
    - Download Bootloader manually  (Download zip file)
      https://github.com/adafruit/Adafruit_nRF52_Bootloader/releases
    - Move it in to "C:\Users\...\Documents\ArduinoData\packages\adafruit\hardware\nrf52\0.14.0\tools\adafruit-nrfutil\win32"
    
    - Connect DFU pin to Gnd on device then reset it while 
    
    - Run this command in command line (Set your own COM and File name) ;
        adafruit-nrfutil.exe --verbose dfu serial --package feather_nrf52832_bootloader-0.2.13_s132_6.1.1.zip --port COM12 -b 115200 --             singlebank --touch 1200
    - If successfully uploaded , disconnect DFU and gnd pin then reset again.
    - Device is ready to use.
    
        
        
        
  - Arduino Ide ile yuklerken Bootloader Hatasi :
    Arduino Ide ile yuklerken assagidaki gibi bir hata aliyorsaniz; 
    "Usage: adafruit-nrfutil.exe dfu serial [OPTIONS]
     Error: Invalid value for "-pkg" / "--package": Path "...bootloader/feather_nrf52832/feather_nrf52832_bootloader-             0.2.13_s132_6.1.1.zip"      does not exist.
     Error while burning bootloader."
     
     
   Sorumluluk sizde olmak kaydiyla su adimlari deneyebilirsiniz;
    - Bootloaderi assagidaki siteden indirin  (zip dosyasini indirin)
      https://github.com/adafruit/Adafruit_nRF52_Bootloader/releases
    - Bu klasore konuma kopyalayin to "C:\Users\...\Documents\ArduinoData\packages\adafruit\hardware\nrf52\0.14.0\tools\adafruit- nrfutil\win32"
    
    - Dfu ile gnd uclarini birlestirip ,reset verin
    
    - Bu komutu windows cmd ekraninda kosturun (komut icindeki COM numarasi ve dosya adini elinizdekilere uygun guncelleyin,ayrica cmd exe neredeyse orada olsun ) ;
        adafruit-nrfutil.exe --verbose dfu serial --package feather_nrf52832_bootloader-0.2.13_s132_6.1.1.zip --port COM12 -b 115200 --             singlebank --touch 1200
        
        
     -  Islem basarili tamamlanirsa , onceden birlestirdiginiz dfu ile gnd yi ayirip tekrar reset verin
     -  Kullanima hazir.
