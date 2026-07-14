# Product Backlog

## Objetivo

Melhorar a experiência de utilização dos cronômetros do BabyBuddy, garantindo que seu estado permaneça consistente entre diferentes sessões e dispositivos.

---

# História 1 — Indicar quando um timer já foi encerrado

Como usuário do BabyBuddy,

Quero ser informado quando um timer já tiver sido encerrado em outra sessão,

Para evitar executar ações inválidas e confiar no estado apresentado pela interface.

### Critérios de aceite

- O sistema deve verificar periodicamente se o timer continua ativo.
- Caso a API retorne 404, o cronômetro deve parar de ser atualizado.
- Uma mensagem deve informar que o timer já foi encerrado.
- As ações relacionadas ao timer devem ser desabilitadas.

---

# História 2 — Atualizar automaticamente o estado do timer

**Não implementada**

### História

Como usuário,

Quero que o cronômetro permaneça sincronizado com o servidor,

Para visualizar sempre informações atualizadas.

### Critérios de aceite

- O sistema deve consultar periodicamente a API.
- O tempo exibido deve refletir o estado atual do timer.

---

# História 3 — Reiniciar rapidamente um timer

Como usuário,

Quero reiniciar rapidamente um cronômetro,

Para iniciar uma nova atividade sem criar outro timer manualmente.

### Critérios de aceite

- O botão Reiniciar deve permanecer disponível enquanto o timer existir.
- O novo timer deve iniciar imediatamente.

---

# História 4 — Excluir timers

Como usuário,

Quero excluir timers que não serão mais utilizados,

Para manter minha lista organizada.

### Critérios de aceite

- O usuário deve confirmar a exclusão.
- O timer deve desaparecer da lista após a confirmação.

---

# História 5 — Criar registros utilizando um timer

Como usuário,

Quero utilizar um timer ativo para criar registros de alimentação, sono ou outras atividades,

Para evitar preencher manualmente horários de início e fim.

### Critérios de aceite

- O timer deve preencher automaticamente os horários.
- O registro deve utilizar a duração calculada pelo timer.
