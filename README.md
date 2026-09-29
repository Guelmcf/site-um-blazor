# SiteUmBlazor

Lista de exercícios da disciplina **Usabilidade, Dev. Web, Mobile e Jogos** (Desenvolvimento Web), com o professor Daniel Henrique Matos de Paiva.

O projeto é uma aplicação **Blazor** (.NET) com quatro páginas. Cada uma exercita um conceito básico do framework: roteamento, eventos de clique, estado e renderização condicional.

## Tecnologias

- .NET 10
- Blazor Web App (render mode **Interactive Server**)
- C# / Razor

## Como rodar

Pré-requisito: [.NET SDK](https://dotnet.microsoft.com/download) instalado.

```bash
git clone https://github.com/SEU-USUARIO/site-um-blazor.git
cd site-um-blazor
dotnet watch
```

Depois de iniciar, acesse `http://localhost:XXXX` no navegador (a porta aparece no terminal).

## Páginas

| Rota | Arquivo | Conceito |
|------|---------|----------|
| `/sobre` | `Components/Pages/Sobre.razor` | Roteamento com `@page` |
| `/contador` | `Components/Pages/Contador.razor` | `@code` e `@onclick` |
| `/mensagem` | `Components/Pages/Mensagem.razor` | Estado booleano e `@if` |
| `/placar` | `Components/Pages/Placar.razor` | Múltiplos eventos alterando o mesmo estado |

### Exercício 1: Sobre Mim
Página estática com um `<h1>` que traz o nome completo e um parágrafo sobre o curso e os interesses de estudo. Mostra como a diretiva `@page` transforma um componente em uma página navegável.

### Exercício 2: Contador de Cliques
Exibe `Número de cliques: X` e um botão **Clique Aqui**. O evento `@onclick` chama o método `Incrementar`, que soma 1 à variável `quantidade`, e a tela se atualiza automaticamente.

### Exercício 3: Alternador de Mensagem
Um botão chama `AlternarVisibilidade`, que inverte a variável `exibirMensagem`. O texto do botão alterna entre **Exibir Mensagem** e **Ocultar Mensagem**. Um bloco `@if` mostra a mensagem *"Bem-vindo ao desenvolvimento web com .NET 10!"* apenas quando o valor é `true`.

### Exercício 4: Placar Interativo
Um placar com três botões: **Somar 1 Ponto**, **Subtrair 1 Ponto** e **Zerar Placar**. O placar nunca fica negativo, porque o método de subtrair só decrementa quando `pontos > 0`.

## Observação sobre interatividade

A partir do .NET 8, os componentes Blazor são renderizados de forma estática por padrão. Por isso as páginas com eventos (Contador, Mensagem e Placar) declaram:

```razor
@rendermode InteractiveServer
```

Sem essa linha, os botões não respondem aos cliques.

## Autor

- Miguel [Sobrenome]
