# Infrasound-Monitor-3DP
Low cost infrasound monitor using i2c digital differential pressure sensor - updated with 3D printed enclosure and other parts.

This fork of starfishprime101's project intends to refresh the build instructions and BOM for the electronics, and include 3D printable design files for enclosures and other parts where possible.  The goal is to lower the project cost and difficulty for anyone with access to a 3D printer.


# Draft of setup and use instructions below - please note this is a work in progress and may contain errors
Assumptions, required skills, and equipment access
    This guide assumes you have some moderate familiarity with technical tasks such as installing an OS on a SD card for the Raspberry Pi, using tools like SSH for basic command line operations (with instructions), handling electronics hardware safely, through-hole soldering, connecting low-voltage electrical power and sensor cables, understanding basic concepts about wireless networking and similar things that are involved in a moderate complexity Raspberry Pi or SBC based project.  If you are not comfortable with these things, searching for them online will yield many video and written guides, and reference links used throughout the guide will generally provide more context and help completed related steps, however it is beyond the scope of this guide to fully educate users on these topics, so continue at your own risk - some steps may result in damage to parts if not done correctly.


   Equipment needed for this project:
        3D Printer - only needed for a few small parts, so access to one through a friend or at a local library or hackerspace/workshop would be sufficient.
        Soldering tools - at a minimum, a 20 watt soldering iron is recommended (40 watts or more if using lead-free solder), as well as solder and a safe workspace with ventilation away from flammable material to do the soldering.
        Basic hand tools - screw driver/hex key wrenches, etc. 
        Computer - access to some laptop or desktop with SD Card slot or a USB-SD card adapter needed to do the Rasberry Pi 

   Use case assumptions
        This guide assumes 
        
   Location: This guide is based on sourcing, building, and testing in the USA.  Most software setup steps are easily adaptable to other locales using reference links throughout or quickly located with keyword searches online.  Sourcing fully equivalent parts outside North America or Europe may be challenging and involve substitutions that require a greater level of technical understanding not covered in this guide.
        
Acquiring Materials
    Parts list with recommended links and approximate prices are listed in "Infrasound 3DP BOM.ods".  Purchase or make parts as listed.
    Note on the Raspberry Pi selection
        A Raspberry Pi 3B is on the parts list because it is widely available new and on the used market for a reasonable price, and is confirmed to be adequate for this project.
        Newer Raspberry Pi models should work as good or better, if desired or if they are more easily available in your location.
        Many other single-board-computers (SBC) with GPIO connections and I2C compatibility are available that will likely work with similar setup steps and parts (Orange Pi, Banana Pi, Rock Pi, Raspberry Pi Zero 2W), but I have not tested other devices and these will not be covered in this guide.

Initial Setup
   Raspberry Pi OS install
    
   Using a terminal run each of the following commands

    sudo raspi-config
 
        3 Interface Options
        I5 I2C - enable i2c for the sensor
        Back > Exit

   System update

        sudo apt-get update
        sudo apt-get dist-upgrade
        
       [reboot recommended]


    
   Obspy - install via Anaconda
        https://github.com/obspy/obspy/wiki/Installation-via-Anaconda
        -or-

            wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-aarch64.sh
            chmod +x Miniconda3-latest-Linux-aarch64.sh
            ./Miniconda3-latest-Linux-aarch64.sh
    
   Original python install packages - Not sure if this is still needed after anaconda install
    
        sudo apt install python3-pip python3-numpy python3-scipy python3-matplotlib python3-lxml python3-setuptools python3-sqlalchemy python3-decorator python3-requests
    
    
   Install other related packages

        sudo apt install python3-smbus python3-serial


Time setup
    Correct time and time-zone settings are important for being able to identify sensor data after capturing it, and confirming it covers a time or event of interest.
    If you plan to always use the device where it will have a wifi connection with internet access, the default configuration includes an automatic network time setting.  All you have to do is confirm time zone is set correctly with:
        sudo raspi-config
            5 Localization Options
            L2 Timezone
    If you plan to use the device in remote locations or without an internet connection you can use a GPS module, or an RTC module to acquire or continually keep the time.
        The GPS module has the advantage of adding location data to sensor logs in addition to time information, and is explained here in the following steps (note that if you plan to use the device indoors without wifi, underground, etc the RTC option may be better)
            Recommended module: Neo-6M 
            Physical sensor setup
                ...
            Software setup
                ...
        For the RTC option, see the guide here: https://pimylifeup.com/raspberry-pi-rtc/
    
Infrasound sensor and main enclosure setup
    Physical sensor
        Hardware leads
        Backing volume build 
        Main Enclosure build
        Tubing connections
        Wiring connections
        
Capturing infrasound
    TBD
