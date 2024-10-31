# D2 Report
## Status
I am using a Raspberry Pi Zero that has the Raspberry Pi operating system on a micro SD card, I'm currently accessing the OS through an SSH connection with my Mac. I now have all of the hardware and planned software needed for this assignment. I'll soon be able to set up a website using NGINX, that can be accessed by anyone on the local network. Through the website the user will be able to upload a file which will be downloaded by the Raspberry Pi Zero connected to the Photon 3D printer. The hope is to reduce the time required transferring files between computer and 3D printer and eliminating the need for a USB.
## Hardware Proof
![[3dPrinter.jpg]]
![[Hardware.jpg]]
## Cost and Marketability
_This project is targeted towards users who already have a 3D printer, so that will not be added to the cost._
The biggest cost will be the kit for the Raspberry Pi, because the Raspberry Pi isn't using any advanced features the Zero version will work fine for the project. All the software used in this project is open source so there is no cost when using software. Because all data will be transferred over the local network there is no server cost for storing and moving files.
- Raspberry Pi Zero Kit: $35
- Software: Free
## Security Holes
Because files are being transferred over a network there is obvious vulnerabilities because there are 3 possible weak points. The computer sending the information to the website, the Raspberry Pi Zero running the website, and the Photon 3D printer that will be connected to the Raspberry Pi Zero.
### Issues:
- Bad actors could upload malicious files.
- User could accidentally crash Raspberry Pi.
- Bad actors could exploit vulnerabilities on PhotonPrinter.
- Bad actors could gain privileged access on Raspberry Pi.
- Open ports can give external access to the local network.
### Solutions:
- Restrict file types using javascript.
- Restrict file types using server side code.
- Restrict file size.
- Separate data storage on Raspberry Pi Zero into a Docker container.
- Ensure passwords used on Raspberry Pi are robust.