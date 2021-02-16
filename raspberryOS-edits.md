# some RaspberryOS (former _Raspbian_)

### EXCLUDE MICROSOFT:

[more Info (heise.de - german)](https://www.heise.de/news/Raspberry-Pi-OS-Zoff-um-Microsoft-Paketverzeichnisse-nach-Update-5050653.html)

> Wer Microsofts Zugriffsmöglichkeiten auf seinem Raspberry-Pi-OS-Systemen
> (auf eigene Verantwortung!)
> unterbinden will, kommentiert alle Zeilen in "__/etc/apt/sources.list.d/vscode.list__"
> per "#" aus und löscht den GPG-Schlüssel "__/etc/apt/trusted.gpg.d/microsoft.gpg__"
> vom System. Der Befehl "apt-mark hold raspberrypi-sys-mods" sorgt dafür,
> dass das inkriminierte Paket nicht automatisch durch eine neue Version ersetzt wird,
> nachdem man die Repos deaktiviert hat – der Admin muss "raspberrypi-sys-mods"
> später aber zumindest einmal händisch aktualisieren, falls er das Paket doch aktualisieren möchte.
> 
> Wer die "harte Tour" bevorzugt, verbietet Änderungen an den beiden genannten Dateien in
> "/etc/apt" mittels "__sudo chattr +i__", riskiert damit allerdings, dass APT das genannte Paket
> später nicht aktualisieren kann und mit einer Fehlermeldung abbricht.

#### CLI input:
```bash
sudo nano /etc/apt/sources.list.d/vscode.list
sudo chattr +i /etc/apt/sources.list.d/vscode.list
sudo truncate -s 0 /etc/apt/trusted.gpg.d/microsoft.gpg
sudo chattr +i /etc/apt/trusted.gpg.d/microsoft.gpg
```

------------------------

### Python stuff

#### F**KING PIP (why are you not included?)

```bash
sudo apt install python3-pip
```

#### She-bang!
##### _cause i forgot it!_ yeah...really...

```python3
#!/usr/bin/python3
```

#### Python GPIO connection:
##### (better then RPi.GPIO)

```bash
sudo apt install python3-gpiozero
```