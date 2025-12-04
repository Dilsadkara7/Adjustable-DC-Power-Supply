# 300W Adjustable Bench Power Supply (Prototype)

This project demonstrates how to build a cost-effective, high-power laboratory power supply by recycling an old computer ATX PSU and integrating a DC-DC Boost Converter.

## 🎯 Objective
To create a versatile **30V 10A power source** for testing electronics, motors, and Hyperloop linear motor systems using upcycled e-waste.

## 🛠️ Tech Specs & Components
- **Input Source:** Upcycled 350W ATX Computer Power Supply (Modified for 12V Rail).
- **Voltage Regulation:** 1800W 20A DC-DC Step-Up (Boost) Converter.
- **Output Range:** 12V - 50V Adjustable / 0 - 10A Adjustable.
- **Interface:** Digital Voltmeter & Ammeter Display.
- **Cooling:** Active cooling with stock ATX fan + Passive aluminum heatsinks.
- **Safety Features:** - XT30 "Ignition Key" Safety Switch System.
  - Reinforced internal cabling with XT60 connectors.
## ⚠️ Disclaimer
This project involves modifying high-voltage (220V) equipment. Safety protocols were strictly followed during the build.

graph TD
    %% Bileşenler
    PSU[ATX GÜÇ KAYNAĞI]
    BOOST[1800W BOOST CONVERTER]
    SWITCH{METAL ANAHTAR}
    LOAD[YÜK / ÇIKIŞ (XT60)]

    %% Stiller
    style PSU fill:#ddd,stroke:#333,stroke-width:2px
    style BOOST fill:#ffcccc,stroke:#f00,stroke-width:2px
    style SWITCH fill:#ff9,stroke:#333
    
    %% Güç Akışı
    PSU == Sarı Demet (+12V) ==> BOOST_IN_PLUS(Boost IN +)
    PSU == Siyah Demet (GND) ==> BOOST_IN_MINUS(Boost IN -)
    
    %% Kontrol
    PSU -- Yeşil Kablo --> SWITCH
    SWITCH -- Siyah Kablo --> PSU_GND(PSU GND)
    
    %% Çıkış
    BOOST_OUT_PLUS(Boost OUT +) == Kırmızı Kablo ==> LOAD
    BOOST_OUT_MINUS(Boost OUT -) == Siyah Kablo ==> LOAD
    
    %% Ayar (Manuel)
    TRIMPOT_V((Mavi Vida - Voltaj)) -.-> BOOST
    TRIMPOT_C((Mavi Vida - Akım)) -.-> BOOST
