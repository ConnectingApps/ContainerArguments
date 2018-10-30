# ContainerArguments

This solution shows how build arguments can be used in Docker. A docker build can be done by setting the folder arguments correctly in the image build. This is done here:

```bash
git clone https://github.com/ConnectingApps/ContainerArguments.git
cd ContainerArguments
cd ContainerArguments
docker build --build-arg inputfolder="" --build-arg outputfolder="/ContainerArguments/" -t ca .
docker run -p 5001:80
```
Visit http://localhost:5001/api/values to see some results.

Alternatively, we can use docker compose. We do not need to set the build arguments. It is done from a different directory (the one with the compose file). In this case we can simply use the default value of the arguments. Test it like this

```bash
git clone https://github.com/ConnectingApps/ContainerArguments.git
cd ContainerArguments
docker-compose up
```
Visit http://localhost:5000/api/values to see some results.

