# Comandos Utilizados

## Trabajo Práctico Integrador
### Arquitectura de Sistemas Operativos

Este documento reúne los principales comandos utilizados durante la implementación, configuración y validación del laboratorio desarrollado para el Trabajo Práctico Integrador.

---

# 1. Información del Sistema

## Identificación del sistema operativo

```bash
hostnamectl
```

## Información del kernel

```bash
uname -a
```

## Información de la distribución

```bash
lsb_release -a
```

## Dirección IP

```bash
ip a
```

---

# 2. Actualización del Sistema

```bash
sudo apt update
```

```bash
sudo apt upgrade -y
```

---

# 3. Instalación del Servicio SSH

```bash
sudo apt install openssh-server -y
```

Verificar estado:

```bash
sudo systemctl status ssh
```

Habilitar al inicio:

```bash
sudo systemctl enable ssh
```

Iniciar el servicio:

```bash
sudo systemctl start ssh
```

---

# 4. Configuración de Fail2Ban

Instalación:

```bash
sudo apt install fail2ban -y
```

Copiar configuración base:

```bash
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
```

Editar configuración:

```bash
sudo nano /etc/fail2ban/jail.local
```

Reiniciar servicio:

```bash
sudo systemctl restart fail2ban
```

Habilitar al inicio:

```bash
sudo systemctl enable fail2ban
```

Estado del servicio:

```bash
sudo systemctl status fail2ban
```

---

# 5. Verificación de Fail2Ban

Estado general:

```bash
sudo fail2ban-client status
```

Estado del jail SSH:

```bash
sudo fail2ban-client status sshd
```

Consultar configuración:

```bash
sudo fail2ban-client get sshd maxretry
```

```bash
sudo fail2ban-client get sshd findtime
```

```bash
sudo fail2ban-client get sshd bantime
```

Desbloquear una dirección IP:

```bash
sudo fail2ban-client set sshd unbanip <IP>
```

---

# 6. Monitoreo de Registros

Registros del servicio SSH:

```bash
sudo journalctl -u ssh
```

Monitoreo en tiempo real:

```bash
sudo journalctl -f -u ssh
```

Registros de autenticación:

```bash
sudo tail -f /var/log/auth.log
```

Registros de Fail2Ban:

```bash
sudo tail -f /var/log/fail2ban.log
```

---

# 7. Verificación de Conectividad

Ping:

```bash
ping <IP_SERVIDOR>
```

Conexión SSH:

```bash
ssh adminlab@<IP_SERVIDOR>
```

---

# 8. Reconocimiento con Nmap

Escaneo básico:

```bash
nmap <IP_SERVIDOR>
```

Escaneo del puerto SSH:

```bash
nmap -p 22 <IP_SERVIDOR>
```

Detección de servicios:

```bash
nmap -sV -p 22 <IP_SERVIDOR>
```

Escaneo avanzado:

```bash
sudo nmap -A <IP_SERVIDOR>
```

---

# 9. Simulación del Ataque

Creación del diccionario:

```bash
nano passwords.txt
```

Verificar Hydra:

```bash
hydra -h
```

Ataque de fuerza bruta:

```bash
hydra -V -t 1 -l adminlab -P passwords.txt ssh://<IP_SERVIDOR>
```

Guardar salida del ataque:

```bash
hydra -V -t 1 -l adminlab -P passwords.txt ssh://<IP_SERVIDOR> | tee hydra.log
```

---

# 10. Comandos de Git

Clonar repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
```

Estado:

```bash
git status
```

Agregar archivos:

```bash
git add .
```

Commit:

```bash
git commit -m "Descripción del cambio"
```

Enviar cambios:

```bash
git push origin main
```

---

# Observaciones

Los comandos incluidos en este documento corresponden a los utilizados durante la implementación y validación del laboratorio desarrollado para el Trabajo Práctico Integrador. Dependiendo de la versión de Ubuntu, Kali Linux o de las herramientas empleadas, algunos parámetros pueden variar ligeramente.