# PyTEA-ECB-CBC
Explore the Tiny Encryption Algorithm (TEA) in ECB and CBC modes using Python. This project visualizes TEA's impact on image security, demonstrating how different modes affect data protection and pattern visibility.

# TEA Encryption Project

## Introduction
This project implements the Tiny Encryption Algorithm (TEA) in both ECB and CBC modes using Python.

### tea.py
This file contains the core implementation of the TEA algorithm. The TEA class includes methods for both encryption and decryption of 64-bit blocks using a 128-bit key.

#### Key Components:
- **Initialization**: The constructor initializes the key and sets up constants like DELTA and ROUNDS.
- **encrypt_block**: This method encrypts a 64-bit block using the TEA algorithm. It processes the left and right halves of the block through multiple rounds of the Feistel network.
- **decrypt_block**: This method decrypts a 64-bit block using the reverse process of the encryption method.

### ecb_mode.py
This file contains the implementation of the ECB mode using the TEA algorithm. The ECBmode class utilizes the TEA class for block encryption and decryption.

#### Key Components:
- **encrypt**: This method takes a list of 64-bit blocks and encrypts each block independently using TEA.
- **decrypt**: This method takes a list of encrypted 64-bit blocks and decrypts each block independently.

### cbc_mode.py
This file contains the implementation of the CBC mode using the TEA algorithm. The CBCmode class also uses the TEA class but introduces an initialization vector (IV) and chaining mechanism for block encryption and decryption.

#### Key Components:
- **Initialization**: The constructor initializes the TEA object and the IV.
- **encrypt**: This method encrypts a list of 64-bit blocks using the CBC mode. Each block is XORed with the previous encrypted block before encryption.
- **decrypt**: This method decrypts a list of encrypted 64-bit blocks using the CBC mode. Each block is decrypted and then XORed with the previous encrypted block to retrieve the plaintext.

### main.py
This is the main script that ties everything together. It loads the input image, processes it into blocks, and performs encryption and decryption using both ECB and CBC modes. The results are saved as new image files.

#### Key Components:
- **load_image_as_blocks**: Loads an image and converts it into 64-bit blocks.
- **save_blocks_as_image**: Converts 64-bit blocks back into an image and saves it.
- **process_image_blocks**: Processes image blocks using the specified encryption/decryption mode.
- **main**: The main function that coordinates loading the image, performing encryption and decryption, and saving the results.

### images/
This directory contains the test image (`Aqsa.bmp`) and the resulting encrypted and decrypted images:
- `ecb_encrypted.bmp`
- `ecb_decrypted.bmp`
- `cbc_encrypted.bmp`
- `cbc_decrypted.bmp`

## How to Run the Code
1. Place the image you want to test in the `images` directory.
2. Run the `main.py` script:
```sh
python main.py
## Requirements
- Python 3.x
- numpy
- Pillow

## Setup
Install the required libraries using pip:
```sh
pip install numpy Pillow

