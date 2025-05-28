Looking into how to send and receive data through BLE on the Raspberry Pi Pico W

Steps for a Windows PC:
1. Install VSCode (make sure to add to PATH)
2. Install the "Raspberry Pi Pico" extension on VSCode
3. Install CMake, Git, ARM GCC toolchain (arm-none-eabi-gcc) and Make
    a. Install MSYS2 and link it with VSCode
    b. Run "pacman -S mingw-w64-x86_64-toolchain make cmake git" in MSYS2
4. Set up the Pico SDK
    a. Run the following:
    ```
    cd ~
    mkdir pico
    cd pico
    git clone -b master https://github.com/raspberrypi/pico-sdk.git
    cd pico-sdk
    git submodule update --init
    ```
    b. Add the following line in MSYS2's ".bashrc" file
    ```
    echo 'export PICO_SDK_PATH=~/pico/pico-sdk' >> ~/.bashrc
    source ~/.bashrc
    ```