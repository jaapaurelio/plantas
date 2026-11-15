# 🌿 Plantas da Casinha

Registo simples das plantas de casa (Laredo, Cantábria). Tudo em ficheiros Markdown,
guardado no GitHub. O "motor" é o Claude Code: abro a pasta e falo com ele.

## Estrutura

```
plantas/
  <nome-da-planta>/
    planta.md     ← ficha: o que é, onde está, vaso, como cuidar
    diario.md     ← registo do dia-a-dia (regas, adubo, observações)
    fotos/        ← fotos com a data no nome: AAAA-MM-DD.jpg
calendario.md     ← tarefas futuras de todas as plantas (transplantes, adubo…)
```

## Uso diário (dentro do Claude Code)

| Comando | Para quê |
|---|---|
| `/regar strelitzia` | regista uma rega de hoje |
| `/registar strelitzia folha nova a sair` | qualquer outra nota no diário |
| `/estado` | que plantas precisam de atenção hoje / esta semana |
| `/nova-planta` | adicionar uma planta (com foto) |

Ou simplesmente escrever em linguagem normal: *"reguei a strelitzia e a monstera"*.

## Google Calendar

As tarefas aparecem no calendário **Plantas** da conta Google. Para marcar uma como feita no telemóvel,
põe `✅` no início do título do evento; da próxima vez que correr `/estado` (ou disser *"sincroniza"*), o Claude regista-a no diário.

Depois: `git add -A && git commit -m "regas" && git push`
(ou pedir ao Claude: *"faz commit e push"*).
