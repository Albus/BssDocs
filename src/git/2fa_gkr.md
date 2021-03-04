# [Двухфакторная аутентификация GitHub][1] и Gnome-Keyring

Для начала нужно создать нa сайте GitHub [Personal Access Token][2], его мы будем использовать вместо стандартного пароля от учетной записи.

Токен нужно както хранить в системе и защищать его от кражи. Первое очевидное решение - использовать стандартное хранилище пользовательских паролей - Gnome-Keyring. Расширение Gnome-Keyring для git не поставляется предварительно скомпилированным, поэтому вы должны скомпилировать и установить его самостоятельно (спасибо [James Ward][3] за инструкцию):

```bash
sudo apt-get install libgnome-keyring-dev
cd /usr/share/doc/git/contrib/credential/gnome-keyring
sudo make
sudo rm git-credential-gnome-keyring.o
sudo mv git-credential-gnome-keyring /usr/bin
git config --global credential.helper gnome-keyring
```
Теперь, если вы **включаете свое имя пользователя в URL**, git сохранит ваш пароль в связке ключей Gnome.

```bash
$ git clone https://MarkLodato@github.com/MarkLodato/scripts
```

[1]: https://help.github.com/articles/about-two-factor-authentication
[2]: https://github.com/settings/applications
[3]: http://stackoverflow.com/a/14528360/303425
