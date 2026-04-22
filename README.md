# 🔐 Brute Force Lab com Kali Linux | Medusa | DVWA | SMB

## 📌 Descrição

Este projeto demonstra a execução de ataques de força bruta em um ambiente controlado utilizando Kali Linux contra a máquina vulnerável Metasploitable 2.

Foram explorados três cenários:

* FTP (brute force)
* Aplicação Web (DVWA)
* SMB (password spraying)

---

## 🛠️ Ferramentas utilizadas

* Kali Linux
* Nmap
* Medusa
* DVWA
* Metasploitable 2
* VirtualBox

---

## 🖥️ Ambiente

* Máquina atacante: Kali Linux
* Máquina alvo: Metasploitable 2
* Rede: Host-only

---

## 🔎 Enumeração

Foi realizada a enumeração de serviços com Nmap:

```bash
nmap -sV <IP_DO_ALVO>
```

### Serviços encontrados:

* FTP (21)
* HTTP (80)
* SMB (445)

---

## ⚔️ Ataque 1 — FTP Brute Force

```bash
medusa -h <IP_DO_ALVO> -u msfadmin -P wordlist.txt -M ftp
```

### Resultado

Credenciais válidas foram encontradas devido ao uso de senha fraca.

### 📸 Evidência

![FTP Attack](images/ftp.png)

### 🔐 Mitigação

* Senhas fortes
* Bloqueio após tentativas
* MFA

---

## 🌐 Ataque 2 — DVWA (Web)

### Procedimento

* Configurado nível LOW
* Testadas múltiplas credenciais

### Resultado

Login realizado com:

* admin / password

### 📸 Evidência

![DVWA Attack](images/dvwa.png)

### ⚠️ Vulnerabilidade

* Sem limitação de tentativas
* Sem CAPTCHA

### 🔐 Mitigação

* CAPTCHA
* Rate limiting
* MFA

---

## 🖧 Ataque 3 — SMB Password Spraying

```bash
medusa -h <IP_DO_ALVO> -U users.txt -p msfadmin -M smbnt
```

### Resultado

Credenciais identificadas testando uma senha comum em múltiplos usuários.

### 📸 Evidência

![SMB Attack](images/smb.png)

### 🔐 Mitigação

* Bloqueio de conta
* Monitoramento de login
* Senhas fortes

---

## 🧠 Conceitos Importantes

* **Brute Force:** várias senhas para um usuário
* **Password Spraying:** uma senha para vários usuários

---

## 📁 Estrutura do Projeto

/images → capturas de tela
wordlist.txt → lista de senhas
users.txt → lista de usuários

---

## 🚀 Conclusão

Este projeto demonstra como sistemas mal configurados podem ser explorados com técnicas simples de ataque, reforçando a importância de boas práticas de segurança.

---

## 👨‍💻 Autor

Diego Franco Ferreira
https://github.com/diego-ff
