# Instruções para o Claude

Este repositório é um diário de plantas de casa. O dono vive em **Laredo, Cantábria (Espanha)**:
clima atlântico ameno e húmido, invernos frescos (raramente geada), verões suaves.
Fala comigo em **português de Portugal**.

## Regras dos ficheiros
- Uma pasta por planta em `plantas/<slug>/` (slug curto, minúsculas, com hífens: `strelitzia-varanda`).
- `planta.md` = ficha fixa (espécie, localização, vaso, cuidados por estação). Só se altera quando algo muda (novo vaso, nova localização, aprendizagem nova).
- `diario.md` = registo cronológico, **uma linha por evento, a mais recente no fim**, neste formato:
  `- AAAA-MM-DD · tipo · nota`
  Tipos: `rega`, `adubo`, `transplante`, `poda`, `praga`, `foto`, `nota`.
- Fotos em `plantas/<slug>/fotos/AAAA-MM-DD.jpg`. Ao registar uma foto, olha para ela e escreve no diário uma observação curta sobre o estado da planta.
- `calendario.md` = tarefas futuras de todas as plantas, ordenadas por data. Quando uma tarefa é feita, risca-a (`~~…~~`) e regista-a no diário da planta.
- Se o utilizador disser apenas "hoje", usa a data atual. Se mencionar uma planta pelo nome comum ("a ave-do-paraíso"), procura a pasta certa.

## Google Calendar (calendário "Plantas")
O calendário Google é a vista do dono sobre as tarefas; os ficheiros continuam a ser a fonte da verdade.
- Usa sempre o calendário com o nome **Plantas**: `b8efabeb9349de06e583454ba782aa00d7a2e2c0bbba2a6c2efed6e0bb78b5b2@group.calendar.google.com`
  (se falhar, procura-o pelo nome com `list_calendars`). Nunca escrevas noutros calendários.
- Ao criar/editar eventos usa `notificationLevel: NONE` e `availability: FREE` (não bloqueia a agenda).
- **Cada tarefa = um evento de dia inteiro**, sem repetição automática, título `<emoji> <Tarefa> · <Planta>`
  (💧 regar/ver terra, 🌱 adubo, 🪴 transplante, ✂️ poda, 🐛 pragas, 👀 verificar). Na descrição: o porquê, curto, e `slug: <slug>`.
- No `calendario.md`, cada linha com evento termina com `[gcal:<eventId>]`.
- **Feito = título começa por `✅`** (o dono pode fazê-lo no telemóvel, ou eu faço-o).
- **Quando o dono diz que fez algo:** regista no diário, risca no `calendario.md`, põe `✅` no evento e,
  se for rega/adubo, cria o próximo evento segundo a frequência da estação.
- **Sincronizar** (no início de `/estado` e sempre que o dono pedir): lista os eventos do calendário Plantas
  das últimas 4 semanas até daqui a 3 meses. Para cada evento com `✅` que ainda não esteja riscado no `calendario.md`:
  regista no diário com a data do evento, risca a linha e cria o seguinte se for tarefa periódica.
  Eventos novos criados pelo dono → acrescenta-os ao `calendario.md`. Eventos mudados de dia → atualiza a data.
- Manter só as próximas 2–3 semanas de regas no calendário; tarefas pontuais (transplante, etc.) podem ir mais longe.

## Ao responder "que precisa de atenção?"
0. Sincroniza primeiro com o calendário Plantas (ver acima).
1. Lê a ficha e o fim do diário de cada planta.
2. Compara o tempo desde a última rega com a frequência da ficha **para a estação atual**.
3. Vê o `calendario.md` para as próximas 2 semanas.
4. Responde curto: lista de plantas a regar / tarefas, e porquê.

## Objetivo
O dono quer **aprender** durante o primeiro ano. Quando fizer sentido, explica brevemente o porquê
de um cuidado e acrescenta aprendizagens úteis à secção "Notas aprendidas" da ficha.
Mantém tudo simples: nada de bases de dados, scripts ou dependências sem necessidade.
