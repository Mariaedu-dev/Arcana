# 🧙 ARCANA — Jornada do Conhecimento

> Um aplicativo de produtividade gamificado onde o usuário evolui como um mago à medida que estuda.

---

## 📌 Sobre o Projeto

O **Arcana** é um aplicativo de organização de estudos com elementos de gamificação.

Esta versão (**v1.0.0**) é totalmente frontend, construída com:

- HTML5  
- CSS3  
- JavaScript (Vanilla)  
- LocalStorage (persistência no navegador)

⚠️ Não possui backend nesta versão.

---

## 🎯 Objetivo da v1.0.0

Criar uma base funcional do sistema contendo:

- Criação de missões
- Cronômetro de estudo
- Sistema de XP
- Evolução de nível
- Barra de progresso semanal
- Ranking local simulado
- Persistência via LocalStorage

---

## 🧠 Conceito

O usuário assume o papel de um mago aprendiz.

Quanto mais estuda:
- Ganha XP
- Sobe de nível
- Evolui visualmente
- Sobe no ranking

Se negligenciar os estudos:
- Pode perder progresso
- Pode cair no ranking

---

## 🏗 Estrutura do Projeto
arcana-app/     
│
├── index.html  
├── css/  
│ └── style.css  
├── js/   
│ ├── app.js     
│ ├── timer.js    
│ ├── xp.js     
│ ├── ranking.js    
│ └── storage.js    
└── assets/   

---

## ⚙️ Funcionalidades

### 🎯 Missões

Usuário define:
- Nome da matéria
- Meta de horas

Missão é armazenada no LocalStorage.

---

### ⏱ Cronômetro

- Iniciar
- Pausar
- Finalizar

Ao finalizar:
- Horas são registradas
- XP é calculado
- Progresso semanal é atualizado
- Dados são salvos

---

### ⭐ Sistema de XP

Regras:
- 1 hora = 10 XP  
- 50 XP = sobe 1 nível  

---

### 📊 Barra de Progresso Semanal

Regra:
- Cada 2 horas estudadas = +10%
- Limite máximo: 100%

Exemplo visual:
[██████░░░░] 60%


---

### 🏆 Ranking Local

Lista simulada com jogadores fictícios.

O usuário sobe no ranking conforme aumenta suas horas totais.

---

### 💾 Persistência

Os dados são salvos no LocalStorage:

- Nível
- XP
- Horas estudadas
- Progresso semanal
- Missões
- Último login

---

## 🎨 Estética

Interface inspirada em dashboards minimalistas com temática mística:

- Tons escuros (azul profundo, roxo, dourado)
- Visual elegante
- Sensação de RPG leve
- Interface limpa e moderna

---

## 🔁 Diagrama de Fluxo do Aplicativo

---

### 📊 Fluxo Geral
Usuário entra no app      
↓     
Carregar dados do LocalStorage     
↓     
Existe jogador salvo?      
├── NÃO → Criar jogador padrão       
└── SIM → Carregar dados      
↓     
Renderizar Dashboard       
↓      
Usuário escolhe ação:       
├── Criar Missão      
├── Iniciar Estudo      
├── Ver Ranking      
└── Ver Avatar     

---

### ⏱ Fluxo da Sessão de Estudo
Clicar em "Iniciar Estudo"      
↓      
startTimer()      
↓       
Usuário pode:      
├── Pausar      
└── Finalizar      
↓      
Ao finalizar:        
→ Calcular horas      
→ Atualizar totalHours       
→ addXP()      
→ updateWeeklyProgress()       
→ Salvar no LocalStorage       
→ Atualizar ranking      
→ Re-renderizar Dashboard      

---

### ⭐ Fluxo do Sistema de XP
Recebe horas estudadas       
↓      
Multiplica por 10 (XP)      
↓     
XP >= 50?     
├── NÃO → Atualiza barra de XP     
└── SIM → level++     
xp -= 50     
Atualizar avatar    

---

### 🏆 Fluxo do Ranking
Carregar lista fake de jogadores      
↓      
Inserir jogador atual      
↓      
Ordenar por totalHours      
↓      
Renderizar lista ordenada       

---

### ⚠️ Fluxo de Perda de Progresso
Abrir aplicativo      
↓     
Comparar data atual com lastLogin     
↓      

3 dias?     
├── SIM → Perde XP      
└── NÃO → Mantém     
↓     
7 dias?     
├── SIM → Zera progresso semanal      
└── NÃO → Mantém     
 
---

## 👩‍💻 Autoras

- Maria Eduarda Pereira Vilarim  
- Maria Cecília de Lima e Silva

---

> Todo grande mago começa como aprendiz.
> O conhecimento é a sua magia.

