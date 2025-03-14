**Habilitar Autenticação por Digital no Sudo (Arch Linux)**

### 1. Instalar o suporte a digital
Se ainda não tiver o **fprintd** instalado, instale-o:

```
sudo pacman -S fprintd
```

Depois, reinicie o serviço:

```
sudo systemctl enable --now fprintd
```

---

### 2. Registrar a digital
Adicione sua impressão digital com:

```
fprintd-enroll
```

Siga as instruções e escaneie seu dedo até o processo ser concluído.

---

### 3. Configurar o sudo para aceitar digital
Agora edite o arquivo de autenticação PAM:

```
sudo nano /etc/pam.d/sudo
```

Adicione estas linhas **no topo** do arquivo:

```
auth       sufficient   pam_fprintd.so max_tries=3
auth       required     pam_unix.so try_first_pass
```

**Salvar e sair:**
- **CTRL + X**, **Y**, **Enter**

Isso faz com que o sudo aceite **impressão digital**, permitindo **três tentativas** antes de pedir a senha.

---

### 4. Testar a autenticação
Agora, execute:

```
sudo -i
```

O terminal **pedirá a digital** até três vezes. Se falhar, solicitará a senha normalmente.

---

### 5. (Opcional) Habilitar digital no login do sistema
Se quiser usar a digital também para **logar no sistema**, edite:

```
sudo nano /etc/pam.d/system-local-login
```

E adicione **logo no topo**:

```
auth       sufficient   pam_fprintd.so
```

Agora, na próxima vez que iniciar o sistema, poderá usar a **digital em vez da senha**.

