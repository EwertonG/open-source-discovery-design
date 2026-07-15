# Cenários de Teste

## História US-01

Como usuário do BabyBuddy,

Quero ser informado quando um timer tiver sido encerrado em outra sessão,

Para evitar executar ações inválidas e confiar no estado apresentado pela interface.

### Critérios de aceite

**CA-01**

Dado que o timer permanece ativo

Quando a página consulta a API

Então o cronômetro continua sendo atualizado normalmente.

**CA-02**

Dado que o timer foi encerrado em outra sessão

Quando a página consulta a API

Então uma mensagem deve informar que o timer foi encerrado.

**CA-03**

Dado que o timer foi encerrado em outra sessão

Quando a API retornar erro 404

Então as ações relacionadas ao timer devem ser desabilitadas.

---

## Cenários de teste

### Cenário 1 — Timer ativo

- Dados válidos → o cronômetro continua funcionando normalmente.

### Cenário 2 — Timer encerrado em outra sessão

- Timer encerrado em outra aba → mensagem exibida com sucesso.

### Cenário 3 — Timer encerrado

- Timer inexistente (404) → ações do timer ficam desabilitadas.
