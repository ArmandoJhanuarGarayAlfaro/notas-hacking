# Retos Bandit

# Level 27 → Level 28

## Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
- **Usuario:** bandit27
- **Contraseña:** YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución
```bash
bandit27@bandit:~$ mk temp -d
mk: command not found
bandit27@bandit:~$ mktemp -d
/tmp/tmp.C7W3B6ZMp5
bandit27@bandit:~$
bandit27@bandit:~$ mktemp -d
/tmp/tmp.4SFNRauQoA
bandit27@bandit:~$ cd /tmp/tmp.RH39ki24pd
-bash: cd: /tmp/tmp.RH39ki24pd: No such file or directory
bandit27@bandit:~$ cd /tmp/tmp.4SFNRauQoA
bandit27@bandit:/tmp/tmp.4SFNRauQoA$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
Permission denied, please try again.
bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.4SFNRauQoA$ ls -la
total 112
drwx------    3 bandit27 bandit27   4096 Feb 28 18:32 .
drwxrwx-wt 3010 root     root     106496 Feb 28 18:33 ..
drwxrwxr-x    3 bandit27 bandit27   4096 Feb 28 18:33 repo
bandit27@bandit:/tmp/tmp.4SFNRauQoA$ cd repo/
bandit27@bandit:/tmp/tmp.4SFNRauQoA/repo$ ñs
ñs: command not found
bandit27@bandit:/tmp/tmp.4SFNRauQoA/repo$ ls
README
bandit27@bandit:/tmp/tmp.4SFNRauQoA/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/tmp.4SFNRauQoA/repo$
```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| git log | Muestra los commits hechos en el repositorio |

## Referencias
- []