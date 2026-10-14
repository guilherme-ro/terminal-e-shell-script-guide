# Linux & Shell Scripting Cheat Sheet

Um guia de referência rápida e prática para comandos essenciais do terminal Linux e fundamentos de Shell Scripting.

---

## 1. Navegação e Manipulação de Arquivos

| Comando | Descrição | Exemplo |
| :--- | :--- | :--- |
| `pwd` | Mostra o diretório de trabalho atual. | `pwd` |
| `ls` | Lista os arquivos e pastas do diretório. | `ls -la` (detalhado, incluindo ocultos) |
| `cd` | Altera o diretório atual. | `cd /var/www` |
| `mkdir` | Cria um novo diretório. | `mkdir -p projetos/web` |
| `cp` | Copia arquivos ou diretórios. | `cp arquivo.txt backup.txt` |
| `mv` | Move ou renomeia arquivos/diretórios. | `mv velho.txt novo.txt` |
| `rm` | Remove arquivos ou diretórios. | `rm -rf pasta/` (cuidado!) |
| `touch` | Cria um arquivo vazio ou atualiza o timestamp. | `touch script.sh` |

---

## 2. Permissões e Propriedade

| Comando | Descrição | Exemplo |
| :--- | :--- | :--- |
| `chmod` | Altera as permissões de um arquivo/pasta. | `chmod +x script.sh` |
| `chown` | Altera o dono e o grupo de um arquivo. | `chown usuario:grupo arquivo.txt` |

* **Permissões numéricas (`chmod`):**
  * `4` = Leitura (r)
  * `2` = Escrita (w)
  * `1` = Execução (x)
  * *Exemplo:* `chmod 755 arquivo` (Dono: rwx, Grupo: r-x, Outros: r-x)

---

## 3. Visualização e Busca de Texto

| Comando | Descrição | Exemplo |
| :--- | :--- | :--- |
| `cat` | Exibe o conteúdo de um arquivo no terminal. | `cat arquivo.txt` |
| `less` | Visualizador paginado de arquivos grandes. | `less log.txt` |
| `head` / `tail` | Exibe as primeiras ou últimas linhas. | `tail -n 20 log.txt` |
| `grep` | Busca por padrões de texto em arquivos. | `grep "erro" log.txt` |
| `find` | Busca por arquivos e diretórios. | `find . -name "*.log"` |

---

## 4. Processos e Sistema

| Comando | Descrição | Exemplo |
| :--- | :--- | :--- |
| `ps` | Lista os processos em execução. | `ps aux` |
| `top` / `htop` | Monitor de processos em tempo real. | `htop` |
| `kill` | Encerra um processo pelo PID. | `kill -9 1234` |
| `df` | Mostra o uso de espaço em disco. | `df -h` |
| `du` | Mostra o uso de espaço por diretório. | `du -sh /var/log/` |
| `free` | Mostra o uso de memória RAM. | `free -h` |

---

## 5. Redes e Conectividade

| Comando | Descrição | Exemplo |
| :--- | :--- | :--- |
| `ping` | Testa a conectividade com um host. | `ping google.com` |
| `curl` / `wget` | Baixa arquivos ou faz requisições HTTP. | `curl -O https://exemplo.com/file.zip` |
| `netstat` / `ss` | Lista conexões de rede e portas abertas. | `ss -tuln` |
| `ip` | Configura e visualiza interfaces de rede. | `ip a` |

---

## 6. Fundamentos de Shell Scripting

### Estrutura Básica
Todo script shell deve iniciar com um *Shebang* indicando o interpretador.

```bash
#!/bin/bash
# Meu primeiro script shell

echo "Olá, Mundo!"
```

### Variáveis
```bash
NOME="Maria"
IDADE=30

echo "Meu nome é $NOME e tenho $IDADE anos."
```

### Condicionais (`if / else`)
```bash
#!/bin/bash

NOTA=8

if [ $NOTA -ge 7 ]; then
    echo "Aprovado!"
elif [ $NOTA -ge 5 ]; then
    echo "Recuperação."
else
    echo "Reprovado."
fi
```

### Loops (`for` e `while`)

**Loop For:**
```bash
#!/bin/bash

for fruta in maçã banana laranja; do
    echo "Gosto de $fruta"
done
```

**Loop While:**
```bash
#!/bin/bash

CONTADOR=1
while [ $CONTADOR -le 5 ]; do
    echo "Contagem: $CONTADOR"
    ((CONTADOR++))
done
```

### Funções
```bash
#!/bin/bash

saudacao() {
    local nome=$1
    echo "Olá, $nome! Bem-vindo ao script."
}

saudacao "Carlos"
```

---

## 7. Atalhos Úteis do Terminal

* **`Tab`**: Autocompleta comandos e caminhos de arquivos.
* **`Ctrl + C`**: Interrompe o processo/comando atual em execução.
* **`Ctrl + R`**: Busca reversa no histórico de comandos.
* **`Ctrl + L`**: Limpa a tela do terminal (equivalente a `clear`).
* **`Setas Cima / Baixo`**: Navega pelo histórico de comandos anteriores.
