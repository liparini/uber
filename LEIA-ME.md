# 🚗 Controle de Viagens Uber

Sistema para registrar e acompanhar suas corridas de Uber, com dados salvos no **Google Sheets**.

---

## 📁 Arquivos do projeto

```
uber-viagens/
├── index.html                     ← Sistema principal (abra no navegador)
├── codigo-google-apps-script.gs   ← Código do backend no Google
└── LEIA-ME.md                     ← Este arquivo
```

---

## ⚙️ Configuração passo a passo

### 1. Criar a planilha no Google Sheets

1. Acesse [sheets.google.com](https://sheets.google.com)
2. Clique em **+ Em branco** para criar uma nova planilha
3. Dê o nome que quiser (ex: *Viagens Uber*)

---

### 2. Configurar o Google Apps Script

1. Na planilha, clique no menu **Extensões → Apps Script**
2. Uma nova aba abrirá com o editor de código
3. **Apague todo o código** que já existe lá
4. Abra o arquivo `codigo-google-apps-script.gs` em um editor de texto
5. **Copie todo o conteúdo** e cole no editor do Apps Script
6. Clique no ícone de **disquete (💾)** para salvar
7. Dê um nome ao projeto (ex: *ControlViagens*) e confirme

---

### 3. Publicar o Apps Script

1. Clique em **Implantar → Nova implantação**
2. Clique na engrenagem ⚙️ ao lado de "Tipo" e escolha **App da Web**
3. Preencha assim:
   - **Descrição:** Controle de Viagens
   - **Executar como:** Eu (seu e-mail)
   - **Quem tem acesso:** Qualquer pessoa
4. Clique em **Implantar**
5. Clique em **Autorizar acesso** e siga as etapas (pode aparecer aviso do Google — clique em *Avançado → Acessar*)
6. Após autorizar, copie a **URL do app da Web** — parece com:
   ```
   https://script.google.com/macros/s/AKfycb.../exec
   ```

---

### 4. Conectar ao sistema

**Opção A — direto no HTML (recomendado para uso pessoal):**

1. Abra o `index.html` em um editor de texto (Bloco de Notas, VSCode, etc.)
2. Localize esta linha:
   ```javascript
   const SCRIPT_URL = "";
   ```
3. Cole a URL entre as aspas:
   ```javascript
   const SCRIPT_URL = "https://script.google.com/macros/s/SUA_URL_AQUI/exec";
   ```
4. Salve o arquivo

**Opção B — pela interface (sem editar código):**

1. Abra o `index.html` no navegador
2. Clique na aba **Config**
3. Cole a URL do Apps Script no campo e clique em **Salvar e testar conexão**

---

## 🌐 Hospedar no GitHub Pages

1. Crie um repositório **público** no GitHub
2. Faça upload do arquivo `index.html`
3. Vá em **Settings → Pages**
4. Em *Branch*, selecione `main` e clique em **Save**
5. Em alguns minutos seu sistema estará em:
   ```
   https://seuusuario.github.io/nome-do-repositorio
   ```

> ⚠️ Se usar o GitHub Pages, prefira a **Opção A** (URL no código),
> pois a Opção B salva no localStorage do navegador e não viaja com o link.

---

## 💡 Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| ✅ Registrar viagem | Data, valor, finalidade, rota e observação |
| ✅ Google Sheets | Dados salvos em tempo real na planilha |
| ✅ Histórico | Filtro por mês e finalidade |
| ✅ Relatório | Por período com gráfico e tabela resumo |
| ✅ Exportar CSV | Baixa o relatório em `.csv` |
| ✅ Excluir viagem | Remove da planilha pelo sistema |
| ✅ Dark mode | Interface se adapta ao tema do sistema |

---

## ❓ Problemas comuns

**"Não foi possível conectar"**
- Verifique se a URL está correta e entre aspas
- Confirme que o acesso da implantação é *Qualquer pessoa*
- Tente reimplantar o script (Implantar → Gerenciar implantações → ✏️ Editar)

**"Erro de autorização"**
- Execute a função `doGet` manualmente no editor do Apps Script uma vez para re-autorizar

**Os dados sumiram**
- Os dados estão na planilha do Google Sheets, não no navegador
- Abra o Google Sheets para confirmar
