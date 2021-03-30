# Coinrule

Coinrule desktop client for linux.

# Installation

You need to have the latest version of [docker](https://docs.docker.com/get-docker/) installed.

You will have to clone the repository.

```bash
git clone git@github.com:tjventurini/coinrule.git
```

Next you will have pull the [nativefier](https://github.com/nativefier/nativefier) container in order to build the application.

```bash
docker pull nativefier/nativefier
```

Now you can build the electron application using the following command.

```bash
docker run --rm -v /path/to/coinrule-repo:/src -v /tmp:/target nativefier/nativefier --icon /src/icon.png --name coinrule -p linux -a x64 --single-instance --tray https://web.coinrule.com/ /target/
```

Now you can copy the build wherever you want.

```bash
mv /tmp/coinrule-linux-x64 ~/apps/coinrule
```

Now you can add an app launcher as shown below and store it under `~/.local/share/applications/coinrule.desktop`.

```
[Desktop Entry]
Type=Application
Version=1.0
Exec=/home/username/apps/coinrule/coinrule
Name=Coinrule
Comment=Custom coinrule client for linux.
Icon=/home/username/apps/coinrule/icon.png
Terminal=false
Categories=Media
```

Don't forget to refresh the database of application entries afterwards 😉

```bash
update-desktop-database ~/.local/share/applications
```