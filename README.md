# ContainerArguments

This solution shows how build arguments can be used in Docker. A docker build can be done by setting the folder arguments correctly in the image build. This is done here:

```bash
git clone https://github.com/ConnectingApps/ContainerArguments.git
cd ContainerArguments
cd ContainerArguments
docker build --build-arg inputfolder="" --build-arg outputfolder="/ContainerArguments/" -t ca .
docker run -p 5001:80
```
**DO NOT FORGET THE DOT (.) SIGN IN THE BUILD COMMAND**
