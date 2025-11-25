# Windows 11

# Instalação do Windows 11  
Guia completo para instalar o Windows 11 em **pendrive**, **VirtualBox** e **máquina real**, com todos os passos organizados e claros.

---

# 1. Criar a Mídia do Windows 11 (Pendrive Bootável)

### 1.1. Baixar o Criador de Mídia Oficial
Acesse o site oficial:
https://www.microsoft.com/pt-br/software-download/windows11

Vá em **Criar mídia de instalação do Windows 11**  
Clique em **Baixar agora**.

> Recomendações:
- Pendrive de **8 GB ou mais**
- Preferencialmente usar porta **USB azul (3.0)**

### 1.2. Criar o Pendrive Bootável
1. Abra o software baixado.
2. Aceite os termos → **Avançar**.
3. Avance novamente (deixe as opções padrão).
4. Selecione **Unidade flash USB** → Avançar.
5. Escolha o pendrive detectado.
6. Clique em **Avançar** e aguarde o download e criação da mídia.
7. Quando concluir, remova o pendrive.

---

# 2. Instalação via VirtualBox Oracle

## 2.1. Criando a Máquina Virtual
1. Abra o **VirtualBox**.
2. Clique em **Novo**.
3. Nome → escolha qualquer nome.
4. Em **Imagem ISO**, clique em **Outro** e selecione a ISO do Windows 11.
5. (Opcional) **Marque**: *Pular Instalação Desassistida*.
6. Finalize a criação.

## 2.2. Configurações da Máquina Virtual
Selecione a máquina criada → **Configurações** → Ativar modo **Expert**.

### Geral → Avançado
- Habilitar **Bi-direcional** nas duas opções.

### Sistema → Placa-mãe
- Ajustar **Memória Base** até o limite da barra verde (sem entrar no vermelho).

### Sistema → Processador
- Colocar até **4 CPUs** no máximo.
- Ativar as opções de **Recursos estendidos**.

### Display
- Habilitar **Aceleração 3D**.
- Colocar **Memória de vídeo no máximo**.

### Rede
- Em *Conectado a*: selecionar **Não conectado** (instalação limpa).

Clique em **OK**.

---

# 3. Iniciar a Instalação no VirtualBox

1. Inicie a máquina.
2. Assim que pedir, pressione qualquer tecla rapidamente.

---

# 4. Processo de Instalação do Windows 11

### 4.1. Primeiros Passos
- Escolha o idioma → **Avançar**.
- Teclado:
  - Com "ç" → **ABNT2**  
  - Sem "ç" → **US Internacional**
- Marque *Concordo que tudo será excluído...*
- Clique em **Instalar o Windows 11**.
- Escolha **Não tenho chave**.

### 4.2. Escolher a Versão do Windows
- **Windows 11 Home**
  - Mais básico, limitado e com menos desempenho.
- **Windows 11 Pro**
  - Mais segurança, domínio, melhor desempenho.

Escolha → Avançar.

---

# 5. Caso o Windows bloqueie a instalação (sem requisitos)

Se aparecer mensagem dizendo que não é possível instalar, faça:

**1. Na tela de escolha de versão, pressione:**

**Shift + F10**


**2. No Prompt, digite:**

```
regedit
```

**3. Vá até:**
HKEY_LOCAL_MACHINE > SYSTEM > Setup

**4. Clique com o botão direito em **Setup** → **Novo → Chave****
Nome: **LabConfig**

**5. Na parte direita, crie **DWORD (32 bits)** com os nomes:**

- ByPassTPMCheck
- ByPassSecureBootCheck
- ByPassRAMCheck
- ByPassStorageCheck
- ByPassCPUCheck


**6. Em cada um, clique com o botão direito do mouse, selecione "modificar" e mude o valor de **0 para 1**.**

- Feche o Registro (botão vermelho).

- Continue a instalação normalmente.

---

# 6. Instalação Sem Internet (Instalação Limpa – Recomendado)

Quando o instalador pedir conexão:

1. Pressione:

**Shift + F10**

**2. Digite:**
```
oobe\bypassnro
```


3. Pressione **Enter**.

O Windows reiniciará e permitirá instalar **sem internet**.

Depois:

- Clique em **Não tenho internet**
- Coloque seu nome
- Configure senha (opcional)
- Nas perguntas de privacidade → escolha sempre **Não** ou a 2ª opção.

---

# 7. Finalizar a Instalação no VirtualBox

Após chegar à área de trabalho:

1. Vá no VirtualBox:
   - **Dispositivos → Inserir imagem do CD dos adicionais**
2. No Explorador de Arquivos:
   - Entre na unidade de CD
   - Execute **VBoxWindowsAdditions**
3. Avance até o fim — reiniciará automaticamente.

Sua instalação estará finalizada.

---

# 8. Instalar o Windows 11 em uma Máquina Real

### 8.1. Iniciar a Instalação
1. Plugue o pendrive com o Windows 11.
2. Ligue o PC e pressione a tecla da BIOS:
   - **F12**, **F10**, **DEL**, depende da placa-mãe.
3. Alterar a **ordem de boot**:
   - Coloque o pendrive como **1º dispositivo**.
4. Salve e saia.

### 8.2. Instalação
O processo é igual ao descrito na seção do VirtualBox:

- Seleção de idioma
- Teclado
- Versão do Windows
- Bypass (se necessário)
- Instalação sem internet (opcional, recomendado)

### 8.3. Instalar Drivers
Após o Windows iniciar:

- Instale os drivers da sua máquina.
- Você pode usar:
  - **Driver Booster**
  - Ou drivers oficiais do fabricante.

---

# 9. Pronto!
Seu Windows 11 está instalado, otimizado e pronto para uso.
