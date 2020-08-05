# Notas de estudo sobre ClamAV

![ClamAV](https://i.imgur.com/hVwZD8w.png)

# Install

```sh
sudo apt install clamav clamav-daemon
```

# Scan .rar files

```sh
sudo apt install libclamunrar7
```

# Stop Service

```sh
sudo systemctl stop clamav-freshclam.service
```

# Update

```sh
sudo freshclam
```

# Scan a dir

```sh
clamscan -r /home/henriquead/minha_pasta/
```
