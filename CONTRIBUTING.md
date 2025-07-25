# Contribuindo para o Sistema Operacional TDAH

Antes de tudo, obrigado por considerar contribuir para o TDAH-OS! São pessoas como você que fazem do TDAH-OS uma ferramenta tão incrível para a comunidade TDAH.

## 🤝 Código de Conduta

Este projeto e todos que participam dele são regidos pelo nosso Código de Conduta. Ao participar, espera-se que você respeite este código. 

### Nossos Padrões

- **Seja Gentil**: Estamos todos aqui para nos ajudar mutuamente
- **Seja Paciente**: Lembre-se de que o TDAH afeta cada pessoa de forma diferente
- **Seja Inclusivo**: Receba bem todos os neurótipos e origens
- **Seja Compreensivo**: Nem todos têm os mesmos níveis de energia ou disponibilidade

## 🎯 Como Posso Contribuir?

### Relatando Bugs

Antes de criar relatórios de bugs, verifique os issues existentes, pois você pode descobrir que não precisa criar um novo. Ao criar um relatório de bug, inclua o máximo de detalhes possível:

- **Use um título claro e descritivo**
- **Descreva os passos exatos para reproduzir o problema**
- **Forneça exemplos específicos**
- **Descreva o comportamento observado e esperado**
- **Inclua capturas de tela, se possível**
- **Inclua detalhes do seu ambiente** (SO, versão do Obsidian, etc.)

### Sugerindo Melhorias

Sugestões de melhorias são rastreadas como issues do GitHub. Ao criar uma sugestão de melhoria, inclua:

- **Use um título claro e descritivo**
- **Forneça uma descrição detalhada da melhoria sugerida**
- **Explique por que esta melhoria seria útil para usuários com TDAH**
- **Liste soluções alternativas que você considerou**

### Sua Primeira Contribuição de Código

Não sabe por onde começar? Procure por essas tags nos nossos issues:

- `good first issue` - Issues simples perfeitos para iniciantes
- `help wanted` - Issues onde precisamos de ajuda
- `quick win` - Tarefas pequenas que podem ser completadas rapidamente (ótimo para TDAH!)

### Pull Requests

1. Faça fork do repositório e crie sua branch a partir da `main`
2. Se você adicionou código, adicione testes
3. Se você mudou APIs, atualize a documentação
4. Garanta que os testes passem
5. Certifique-se de que seu código segue nosso guia de estilo
6. Envie esse pull request!

## 📝 Processo de Desenvolvimento

### Configurando Seu Ambiente

```bash
# Clone seu fork
git clone https://github.com/seu-usuario/adhd-operating-system.git
cd adhd-operating-system

# Adicione o remote upstream
git remote add upstream https://github.com/original/adhd-operating-system.git

# Instale as dependências
npm install

# Execute os testes
npm test
```

### Estilo de Código

- Use nomes de variáveis significativos
- Comente lógica complexa
- Mantenha funções pequenas e focadas
- Siga os padrões existentes na base de código

### Mensagens de Commit

Seguimos commits convencionais:

```
feat: adiciona timer pomodoro
fix: corrige cálculo de tempo nas notas diárias
docs: atualiza instruções de configuração
style: formata código com prettier
test: adiciona testes para rastreamento de hábitos
```

### Testes

- Escreva testes para novas funcionalidades
- Garanta que todos os testes passem antes de enviar PR
- Inclua testes unitários e de integração quando apropriado

## 🧠 Dicas de Contribuição Amigáveis ao TDAH

### Dividindo Tarefas

1. **Comece Pequeno**: Escolha uma coisa pequenina para corrigir
2. **Use Cronômetros**: Trabalhe em blocos de 25 minutos
3. **Documente Conforme Avança**: Escreva notas enquanto o contexto está fresco
4. **Peça Ajuda**: Estamos aqui para apoiá-lo!

### Gerenciando Sobrecarga

- Tudo bem enviar PRs incompletos com tag [WIP]
- Faça pausas quando necessário
- Foque em um issue por vez
- Use nosso Discord para ajuda em tempo real

### Gerenciamento de Tempo

- Defina prazos realistas para si mesmo
- Comunique se precisar de mais tempo
- Tudo bem abandonar um PR se perder o interesse

## 📊 Integração Task Master

Usamos o Task Master para gerenciar nossas tarefas de desenvolvimento:

```bash
# Veja as tarefas disponíveis
task-master list

# Pegue uma tarefa da comunidade
task-master next --tag=community

# Acompanhe seu progresso
task-master set-status --id=<task-id> --status=in-progress
```

## 🎉 Reconhecimento

Todos os contribuidores serão adicionados ao nosso arquivo [CONTRIBUTORS.md](CONTRIBUTORS.md) e receberão:

- 🏆 Emblema de contribuidor no Discord
- 📜 Certificado de contribuição
- 💝 Nossa eterna gratidão!

## 📞 Obtendo Ajuda

- **Discord**: Junte-se ao nosso [servidor Discord](https://discord.gg/adhd-os)
- **Discussões**: Use [GitHub Discussions](https://github.com/yourusername/adhd-operating-system/discussions)
- **Horário de Atendimento**: Sessões semanais de ajuda no Discord (Quintas-feiras 19h EST)

## 🔄 Processo de Release

1. Funcionalidades são desenvolvidas em feature branches
2. PRs são revisados por pelo menos um mantenedor
3. PRs aprovados são mesclados na `develop`
4. Releases semanais da `develop` para a `main`
5. Hotfixes vão diretamente para a `main` com backport para a `develop`

## 📚 Recursos Adicionais

- [Roteiro do Projeto](https://github.com/yourusername/adhd-operating-system/projects/1)
- [Documentação de Arquitetura](docs/ARCHITECTURE.md)
- [Documentação da API](docs/API.md)
- [Guia de Testes](docs/TESTING.md)

---

Lembre-se: **Suas contribuições importam, não importa quão pequenas!** Cada correção de bug, funcionalidade ou até mesmo correção de erro de digitação ajuda a tornar o TDAH-OS melhor para todos.

Obrigado por fazer parte da nossa comunidade! 💜