# Avnet Starter Kit
Check [prerequisits](./prerequisites.md) before hands-on labs.
1. Unbox the devkit
1. Connect micro-usb plug with Avnet devkit socket and the other end with laptop's USB type-A socket
1. open Azure Sphere CLI on the laptop
    - recover Azure Sphere OS images. this will take around 90~100 seconds.
    > azsphere device recover
1. login Microsoft account
    > azsphere login
1. Claim your device ([more](https://docs.microsoft.com/en-us/azure-sphere/install/claim-device?tabs=cliv1))
    - claim Azure Sphere device to an Azure Sphere Tenant
1. Configure network setting ([more](https://docs.microsoft.com/en-us/azure-sphere/install/configure-wifi))
1. (*board setting complete*) [go to project](./avnet-lab-azureiot.md)

---
## Avnet dev board block diagram
![](./images/avnet-blockdiagram.jpg)