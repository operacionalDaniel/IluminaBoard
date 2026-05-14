# 💡 Dashboard · Iluminação Pública 2026

Dashboard gerencial para acompanhamento dos **5 indicadores de qualidade contratuais (SLAs)** e **Contraprestação Mensal Efetiva (CME)** de contratos de iluminação pública.

🔗 **Acesse online:** `https://<seu-usuario>.github.io/<nome-do-repositorio>/`

---

## 📊 O que o dashboard apresenta

| Seção | Conteúdo |
|---|---|
| **Financeiro** | CME, CMM, FM e Índice de Eficiência (gauge) |
| **SLAs** | 5 cards com score, % atingido, barra de progresso e contribuição |
| **Análise** | Composição do IE, gráfico de satisfação (Exati), resumo de OS |
| **Evolução Anual** | Gráfico de IE + CME por mês com mês ativo destacado |

### Fórmulas aplicadas

```
PPA  = 1 − (Nf − Ni) / Pt                           → SLA 1 (peso 40%)
PCE  = NCEa / NCEi                                   → SLA 2 (peso 20%)
PCNE = NCNEa / NCNEi                                 → SLA 3 (peso 20%)
TOS  = (1440 × Dm − Ti) / (1440 × Dm)               → SLA 4 (peso 10%)
SAT  = % Ótimo + % Bom                               → SLA 5 (peso 10%)

IE   = (SLA1×0,4) + (SLA2×0,2) + (SLA3×0,2) + (SLA4×0,1) + (SLA5×0,1)
CME  = CMM × FM × IE
```

---

## 🗂 Estrutura do repositório

```
/
├── index.html                    ← Dashboard (abre direto no navegador)
├── template_dashboard_ip_2026.xlsx  ← Planilha de entrada de dados
└── README.md
```

---

## 🚀 Como publicar no GitHub Pages (passo a passo)

### 1. Criar o repositório

1. Acesse [github.com](https://github.com) e faça login
2. Clique em **"New repository"** (botão verde)
3. Escolha um nome (ex: `dashboard-iluminacao-publica`)
4. Marque **"Public"**
5. Clique em **"Create repository"**

### 2. Fazer upload dos arquivos

1. Na página do repositório, clique em **"uploading an existing file"**
2. Arraste os 3 arquivos:
   - `index.html`
   - `template_dashboard_ip_2026.xlsx`
   - `README.md`
3. Clique em **"Commit changes"**

### 3. Ativar o GitHub Pages

1. Vá em **Settings** (engrenagem) → **Pages** (menu lateral esquerdo)
2. Em **"Source"**, selecione: `Deploy from a branch`
3. Em **"Branch"**, selecione: `main` → pasta `/ (root)`
4. Clique em **Save**
5. Aguarde ~2 minutos

### 4. Acessar o dashboard

O link aparecerá no topo da página Pages:
```
https://<seu-usuario>.github.io/<nome-do-repositorio>/
```

---

## 📋 Como usar o dashboard

### Fluxo mensal (5 minutos)

```
1. Abra  template_dashboard_ip_2026.xlsx
2. Localize a linha do mês atual (ex: mai/26)
3. Preencha os campos AZUIS com os dados do mês:
   - CMM e FM (financeiro)
   - Nf, Ni, Pt (falhas IP — SLA 1)
   - NCEi, NCEa (chamados emergência — SLA 2)
   - NCNEi, NCNEa (chamados não emergenciais — SLA 3)
   - Dm, Ti (sistema de telegerenciamento — SLA 4)
   - % Ótimo, Bom, Regular, Ruim + total de ligações (pesquisa Exati — SLA 5)
4. Salve o arquivo
5. Acesse o dashboard online
6. Clique em "⬆ Nova planilha" e importe o arquivo
7. Clique no mês desejado para visualizar
```

### Fontes de dados por SLA

| SLA | Dado necessário | Fonte |
|-----|----------------|-------|
| SLA 1 | Nf, Ni, Pt | Sistema de Telegerenciamento |
| SLA 2 | NCEi, NCEa | Sistema de OS / Call Center |
| SLA 3 | NCNEi, NCNEa | Sistema de OS |
| SLA 4 | Dm, Ti (min) | Log do Sistema de Gerenciamento Remoto |
| SLA 5 | % por classificação + total | Exati (pesquisa de satisfação) |

---

## 🔄 Atualizar os arquivos no GitHub

Para subir uma nova versão da planilha ou do dashboard:

1. Acesse o repositório no GitHub
2. Clique no arquivo que deseja substituir (ex: `template_dashboard_ip_2026.xlsx`)
3. Clique no ícone de lápis ✏️ ou no botão **"..."** → **"Upload new file"**
4. Faça o upload do arquivo atualizado
5. Clique em **"Commit changes"**

A atualização fica disponível em ~1 minuto.

---

## ⚠️ Regras do template Excel

- Não altere os **nomes das colunas** (linha 4 da aba DADOS_MENSAIS)
- Não insira **linhas antes da linha 5** (dados começam na linha 6)
- Formato do mês: `xxx/AA` — ex: `jan/26`, `fev/26`, `mar/26`
- Os campos **Dm (dias no mês)** já vêm preenchidos automaticamente
- Meses sem dados simplesmente **não aparecem** no filtro do dashboard

---

## 🛠️ Tecnologias utilizadas

- **HTML5 + CSS3 + JavaScript** puro — sem frameworks, sem instalação
- **SheetJS (xlsx.js)** — leitura de arquivos Excel no navegador via CDN
- **Google Fonts** — tipografia Barlow Condensed + Barlow
- **Canvas API** — gráfico de evolução anual desenhado nativamente
- **GitHub Pages** — hospedagem gratuita de sites estáticos

---

*Dashboard Gerencial · Iluminação Pública · 2026*
