# LATIS
![image](https://github.com/user-attachments/assets/2c692e7a-9d72-49e4-afac-216685f1fa53)

# StyleGAN Latent Space Explorer

This program allows users to interactively traverse the latent space of StyleGAN networks and stream the generated visuals via Spout to other applications like TouchDesigner. The interaction is handled through OSC (Open Sound Control), enabling real-time control over key parameters such as X/Y coordinates, speed, Psi, and seed. This project is built upon the framework provided by NVIDIA for StyleGAN.

## Features
- **Interactive Latent Space Exploration**: Move through the latent space of a StyleGAN network in real time.
- **OSC Integration**: Control parameters remotely via Open Sound Control (OSC).
- **Spout Integration**: Stream the generated visuals to other applications like TouchDesigner.
- **Adjustable Parameters**:
  - **X/Y Coordinates**: Navigate through the latent space.
  - **Speed**: Control movement velocity.
  - **Psi**: Adjust style strength.
  - **Seed**: Change the base image generation.

## Requirements
- Python 3.10
- pythonosc
- PySpout (built and included in package)
- NumPy, OpenCV, and other relevant dependencies
- PySpout is built with VS code 2022, resulting in CUDA 12.1 or later and PyTorch 2.1 or later. I used CUDA 12.4 and PyTorch 2.5.1 so those should work.

## Usage
1. Start the program:
   ```sh
   python latis.py
   ```
2. Use an OSC-compatible controller (e.g., TouchDesigner, Max/MSP) to send OSC messages.
3. Connect a receiving application via Spout to view the visuals.
4. Adjust parameters dynamically to explore different regions of the latent space.

## OSC Controls
Address : 127.0.0.1 (localhost)
Network Port : 12345
Network Port PSI : 65535
| Parameter | Address        | Description |
|-----------|---------------|-------------|
| X         | `/dx`   | Adjust X coordinate in latent space |
| Y         | `/dy`   | Adjust Y coordinate in latent space |
| Speed     | `/fs` | Control movement speed |
| Psi       | `/psi`  | Modify style strength |
| Seed      | `/sd` | Change base seed for generation |

## Spout Integration
-Spout sender name: GANVisualizer
- Ensure your target application (e.g., TouchDesigner) has a Spout input.
- The generated images are streamed in real time and can be used as a texture or video feed.

## Acknowledgments
- Built on NVIDIA’s StyleGAN framework.
- Uses Spout for real-time video sharing.

## License
MIT License. See `LICENSE` for details.

## Contributing
Feel free to open issues or submit pull requests to improve the project!

---
Enjoy exploring the infinite possibilities of GAN-generated visuals! 🚀


