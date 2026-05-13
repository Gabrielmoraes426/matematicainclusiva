# 🎓 Matemática Inclusiva — Tutor Adaptativo da SESI

Um aplicativo educacional inovador que torna a matemática acessível, inclusiva e divertida para todos os alunos, com atenção especial às necessidades de alunos neurodivergentes, com deficiências e em risco educacional.

## 🌟 Destaques

- ✅ **Personalização por Perfil**: O tutor se adapta ao tipo de deficiência ou transtorno (TEA, TDAH, Síndrome de Down, Paralisia Cerebral, DI, etc.)
- 🎮 **Jogos Educacionais Gamificados**: Fases progressivas com recompensas, sons, confetes e animações
- 🗣️ **Acessibilidade Total**: Textos lidos, interface adaptável, sons amigáveis, cores inclusivas
- 📊 **Rastreamento de Progresso**: Registro automático de desempenho por habilidade
- 📚 **Integração com Livros SESI**: Base de dados de materiais pedagógicos indexados
- 🤖 **Tutor Local em IA**: Claude/GPT local para mediação sem depender de internet
- 👥 **Múltiplos Atores**: Dashboard de educadores, responsáveis e alunos

## 📋 Estrutura do Projeto

```
├── public/
│   ├── index.html                          # HTML raiz
│   └── assets/
│       ├── sesi-logo.png
│       ├── mascot.svg
│       └── sounds/
├── src/
│   ├── App.jsx                             # Componente raiz
│   ├── index.css                           # Estilos globais
│   ├── components/
│   │   ├── Topbar.jsx
│   │   ├── StudentSelector.jsx
│   │   ├── GamePhase.jsx
│   │   ├── Mascot.jsx
│   │   └── ...
│   ├── games/
│   │   ├── Quiz.jsx
│   │   ├── MaterialDourado.jsx
│   │   ├── Fracao.jsx
│   │   ├── Regua.jsx
│   │   ├── Transferidor.jsx
│   │   ├── Pitagoras.jsx
│   │   ├── Sequencia.jsx
│   │   ├── Dinheiro.jsx
│   │   └── Area.jsx
│   ├── data/
│   │   ├── students.json                   # Base de alunos
│   │   ├── phases.json                     # Estrutura de fases
│   │   ├── books.json                      # Livros SESI
│   │   └── skills.json                     # Habilidades
│   └── utils/
│       ├── audio.js                        # Sons e síntese de voz
│       ├── storage.js                      # LocalStorage
│       └── analytics.js                    # Rastreamento
├── package.json
└── .gitignore
```

## 🚀 Como Começar

### 1. Instalação

```bash
# Clone o repositório
git clone https://github.com/Gabrielmoraes426/matematicainclusiva.git
cd matematicainclusiva

# Instale as dependências
npm install

# Inicie o desenvolvimento
npm start
```

### 2. Estrutura de Dados Esperada

#### Aluno (`src/data/students.json`)
```json
{
  "id": "aluno_alice",
  "nome": "Alice dos Santos",
  "ano": "9º Ano",
  "condicao": "TEA – Transtorno do Espectro Autista",
  "apoio": "Estagiário Facilitador",
  "foto": "data:image/jpeg;base64/...",
  "habCognitivo": "Demonstra organização sensorial...",
  "desCognitivo": "Necessita de suporte visual...",
  "avancos": "Progrediu em..."
}
```

#### Fase (`src/data/phases.json`)
```json
{
  "id": "fase_001",
  "titulo": "Conhecendo os Números",
  "descricao": "Aprenda a contar de 1 a 10",
  "mundo": "🌍 Mundo 1",
  "jogo": "contagem",
  "dificuldade": "inicial",
  "prereq": [],
  "xpMin": 100,
  "tutorial": "contagem",
  "apoios": ["visual", "auditivo"]
}
```

## 🎮 Modos de Jogo

### Iniciantes (1º-3º Ano)
- 🔢 **Contagem**: Contar objetos na tela
- 🍕 **Frações Visuais**: Pizzas e bolos
- 📏 **Régua**: Medir comprimentos
- 📐 **Ângulos Básicos**: Transferidor

### Intermediário (4º-6º Ano)
- 🧮 **Material Dourado**: Unidades, dezenas, centenas
- 🔢 **Sequências**: Padrões numéricos
- 💰 **Dinheiro e Troco**: Compras reais
- 🔲 **Área**: Contar quadradinhos

### Avançado (7º-9º)
- 📐 **Pitagoras**: Triângulos retângulos
- 📊 **Gráficos**: Interpretação de dados
- 🧬 **Proporções**: Razão e proporção
- 🎲 **Probabilidade**: Eventos aleatórios

## ♿ Recursos de Acessibilidade

### Para TEA
- ✅ Transições suaves
- ✅ Cores predefinidas
- ✅ Sem piscadas
- ✅ Roteiros visuais

### Para TDAH
- ✅ Fases curtas (2–5 min)
- ✅ Feedback imediato
- ✅ Sons energéticos
- ✅ Recompensas visíveis

### Para Deficiências Intelectuais
- ✅ Instruções simples
- ✅ Muitos exemplos visuais
- ✅ Tempo estendido
- ✅ Apoio do educador

### Para Paralisia Cerebral
- ✅ Controles adaptáveis
- ✅ Modo mão única
- ✅ Teclado/Voz
- ✅ Ajuste de velocidade

## 📱 Componentes Principais

```jsx
<App />
├── <Topbar /> (logo, menu, usuário)
├── <StudentSelector /> (escolher aluno)
├── <TelaSelecao /> (listar fases)
├── <MapaMundo /> (snake path de fases)
├── <GamePhase /> (jogo ativo)
│   ├── <StudentBadge />
│   ├── <QuizGame /> | <Fracao /> | <Area /> ...
│   └── <XPCounter />
├── <TutorialModal />
├── <GuiaBar /> (dicas contextuais)
└── <TurorIA /> (chat com Claude)
```

## 🤖 Integração com IA Tutor

```javascript
// Exemplo de chamada ao tutor local
const tutor = await initializeTutor({
  model: 'claude-3-haiku', // ou GPT local
  context: {
    studentProfile,
    currentSkill,
    recentErrors
  }
});

const resposta = await tutor.chat(
  "Por que 3/4 é maior que 1/2?"
);
```

## 📊 Dashboard de Educadores

- Visualizar progresso por turma
- Filtrar por habilidade / dificuldade
- Exportar relatórios (PDF/Excel)
- Mensagens para pais/responsáveis
- Ajustar dificuldade por aluno

## 🎨 Design System

### Cores Inclusivas
```css
--sage: #4F9968;      /* Verde — segurança */
--coral: #E96B4F;     /* Coral — energia */
--amber: #E8AE2E;     /* Âmbar — alegria */
--sky: #4A82B4;       /* Azul — calma */
--plum: #7E5CC4;      /* Roxo — criatividade */
```

### Tipografia Acessível
- **Atkinson Hyperlegible** (corpo do texto)
- **Space Grotesk** (títulos, números)
- **Baloo 2** (destaques, CTAs)

## 🔊 Acessibilidade Auditiva

```javascript
// Síntese de fala contextual
window.__falar(texto, taxa);

// Sons de feedback
playSuccess();  // ✓ Acertou
playRetry();    // ✗ Tenta de novo
playLevel();    // 🎉 Nova fase
playCoins();    // 💰 Ganhou XP
```

## 💾 Armazenamento Local

```javascript
// Progresso é salvo automaticamente
saveProgress({
  studentId,
  phaseId,
  score,
  timeSpent,
  errors,
  skillsHit
});

// Recuperar histórico
const history = getStudentHistory(studentId);
```

## 🧪 Testes

```bash
# Executar testes unitários
npm test

# Testar acessibilidade
npm run axe

# Build de produção
npm run build
```

## 📈 Roadmap

- [ ] Modo offline com Service Workers
- [ ] Reconhecimento de fala (controle por voz)
- [ ] Integração com Google Classroom
- [ ] Modo multijogador cooperativo
- [ ] Criação de fases customizadas por educador
- [ ] Análise preditiva de dificuldades
- [ ] App mobile (React Native)
- [ ] Suporte a mais idiomas (Espanhol, Inglês)

## 🤝 Contribuindo

1. Fork este repositório
2. Crie uma branch para sua feature (`git checkout -b feature/minha-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciono minha feature'`)
4. Push para a branch (`git push origin feature/minha-feature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob licença **MIT**. Veja `LICENSE` para mais detalhes.

## 👥 Equipe

- **Gabriel Moraes** (@Gabrielmoraes426) — Desenvolvedor Principal
- **SESI Diadema** — Instituição Parceira
- **Educadores Inclusivos** — Consultoria Pedagógica

## 📞 Suporte

Para dúvidas ou sugestões:
- 📧 Email: `suporte@matematicainclusiva.sesi`
- 🐛 Issues: https://github.com/Gabrielmoraes426/matematicainclusiva/issues
- 💬 Discussões: https://github.com/Gabrielmoraes426/matematicainclusiva/discussions

---

**Feito com ❤️ para incluir todos na matemática** 🌟
