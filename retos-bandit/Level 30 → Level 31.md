# Retos Bandit

# Level 30 → Level 31

## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
- **Usuario:** bandit30
- **Contraseña:** xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución
```bash
bandit29@bandit:/$ mkdir /tmp/repo7435
bandit30@bandit:~$ cd /tmp/repo7435
bandit30@bandit:/tmp/repo7435$
bandit30@bandit:/tmp/repo7435$ git clone ssh://bandit30-git@localhost:2220/home/bandi
t30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/repo7435$ ls
repo
bandit30@bandit:/tmp/repo7435$ cd repo/
bandit30@bandit:/tmp/repo7435/repo$ ls
README.md
bandit30@bandit:/tmp/repo7435/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/repo7435/repo$ git log
commit cf552c166d78421e64ddf52f850e680075d216e1 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:13 2023 +0000

    initial commit of README.md
bandit30@bandit:/tmp/repo7435/repo$ git tag
secret
bandit30@bandit:/tmp/repo7435/repo$ git tag -l
secret
bandit30@bandit:/tmp/repo7435/repo$ git checkout secret
fatal: reference is not a tree: secret
bandit30@bandit:/tmp/repo7435/repo$ git lag
git: 'lag' is not a git command. See 'git --help'.

The most similar commands are
        log
        tag
bandit30@bandit:/tmp/repo7435/repo$ git tag
secret
bandit30@bandit:/tmp/repo7435/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/repo7435/repo$

```
## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- [Comandos git](https://www.atlassian.com/es/git/glossary)
- [Git tag](https://www.atlassian.com/es/git/tutorials/inspecting-a-repository/git-tag#:~:text=El%20comando%20git%20tag%20es,valiosos%20adicionales%20sobre%20la%20etiqueta.)
- 