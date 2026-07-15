# Prompts Utilizados

Durante o desenvolvimento do trabalho, foram utilizados os seguintes prompts para apoiar as etapas de análise, planejamento e implementação.

---

## Personas

Crie duas personas para um sistema open source de acompanhamento da rotina de bebês, considerando usuários que utilizam o sistema em diferentes dispositivos.

---

## Mapa de Empatia

Construa um mapa de empatia para uma persona que utiliza um sistema de acompanhamento da rotina de bebês e precisa manter as informações sincronizadas entre múltiplos dispositivos.

---

## Ideação

Sugira diferentes soluções para o seguinte problema:

Um timer permanece sendo exibido como ativo na interface mesmo após ter sido encerrado em outra sessão.

Compare as vantagens e desvantagens de cada solução.

---

## Implementação

Durante o desenvolvimento da contribuição para o BabyBuddy, a Inteligência Artificial foi utilizada como ferramenta de apoio para análise da arquitetura, compreensão da issue, identificação de impactos e revisão da solução proposta.

- Se eu alterar a forma como o model `Timer` salva ou calcula a duração ativa (especialmente no método `duration()`), quais outras entidades ou views do BabyBuddy que consomem esse dado podem ser impactadas?
- Se a API `/api/timers/<id>/` passar a retornar 404 após um timer ser encerrado, qual seria a melhor forma de refletir esse estado na interface do usuário?
- Existe algum risco de interromper o `setInterval()` do cronômetro ao detectar um erro 404? Há algum efeito colateral que deve ser considerado?

---

## Revisão

- Revise esta alteração em JavaScript e indique possíveis problemas de legibilidade, manutenção ou compatibilidade com o padrão utilizado pelo BabyBuddy.
- Analise as alterações realizadas antes da abertura do Pull Request e verifique se elas atendem ao objetivo da issue, possuem baixo acoplamento e seguem o estilo adotado pelo projeto BabyBuddy.
