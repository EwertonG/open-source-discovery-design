## 1. Descrição do sistema

O BabyBuddy é um sistema open source desenvolvido para auxiliar pais, responsáveis e cuidadores no acompanhamento da rotina de bebês. A aplicação permite registrar informações importantes do dia a dia, como alimentação, sono, troca de fraldas, medicação, extração de leite, crescimento e utilização de cronômetros para monitorar atividades em andamento.

Além da interface web, o sistema disponibiliza uma API REST e é mantido por uma comunidade ativa no GitHub, recebendo melhorias e correções continuamente.

---

## 2. Objetivo do sistema

O principal objetivo do BabyBuddy é centralizar o registro das atividades relacionadas aos cuidados com o bebê, facilitando o acompanhamento da rotina por diferentes cuidadores.

A aplicação busca oferecer informações confiáveis e atualizadas, permitindo que pais e responsáveis tenham maior controle sobre os cuidados realizados.

---

## 3. Público-alvo

Os principais usuários do sistema são:

- Pais e mães;
- Responsáveis legais;
- Babás e cuidadores;
- Profissionais de saúde que acompanham o desenvolvimento infantil.

Como o cuidado com o bebê normalmente é compartilhado entre mais de uma pessoa, é comum que o sistema seja utilizado em diferentes dispositivos e navegadores simultaneamente.

---

## 4. Jobs To Be Done (JTBD)

### Job Principal

**Quando estou utilizando o BabyBuddy em mais de um dispositivo ou navegador, quero que o sistema reflita corretamente o estado atual dos cronômetros para evitar informações inconsistentes e impedir ações inválidas.**

### Resultado esperado

O usuário deve sempre visualizar o estado real do cronômetro, mesmo quando ele for encerrado em outra sessão.

---

## 5. Problema identificado

Durante a análise das issues abertas do projeto foi identificada uma inconsistência relacionada aos cronômetros.

O problema ocorre quando um usuário mantém a página de um timer aberta enquanto o mesmo timer é encerrado em outra aba ou dispositivo.

Nessa situação:

1. A API deixa de encontrar o timer ativo;
2. A página continua exibindo o cronômetro em funcionamento;
3. O usuário acredita que o timer ainda está ativo;
4. A interface permite executar ações que já não fazem mais sentido.

Essa inconsistência gera uma experiência confusa e pode levar o usuário a registrar informações incorretas.

---

## 6. Evidências

Nós selecionamos uma issue pública do repositório BabyBuddy descrevendo exatamente esse comportamento.

Issue analisada:

Issue 983 - Indicate that a timer has already been stopped when viewing its detail page.

A proposta sugerida pelos mantenedores era realizar uma verificação leve do estado do timer, exibindo uma mensagem informando que ele já havia sido encerrado e desabilitando as ações relacionadas ao cronômetro.

---

## 7. Solução proposta

A solução implementada consistiu em detectar quando a API retorna erro 404 durante a atualização periódica do cronômetro.

Quando isso ocorre, a interface passa a:

- interromper a atualização do contador;
- exibir uma mensagem informando que o timer já foi encerrado;
- desabilitar as ações relacionadas ao timer (editar, excluir e reiniciar).

Essa abordagem mantém a interface sincronizada com o estado real da aplicação sem alterar o funcionamento normal dos cronômetros ativos.

---

## 8. Justificativa da escolha

A issue foi escolhida pois, representa um problema real reportado pela comunidade, possui escopo reduzido, melhora a experiência do usuário e exige alterações tanto na interface quanto no código JavaScript;
