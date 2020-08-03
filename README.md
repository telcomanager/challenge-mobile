# Telcomanager mobile development challenge

## Descrição

Esse desafio faz parte do processo seletivo da Telcomanager para a vaga de Desenvolvedor de Software - Mobile e com ele poderemos avaliar melhor seu perfil em relação a vaga. O desafio consiste em desenvovler um aplicativo, apenas com a solução para o Front-end, consumindo APIs aqui especificadas.

A tela inicial do aplicativo deve exibir uma lista de alarmes recuperados via API. Esses dados estarão no formato JSON seguindo as seguintes estruturas:

### Lista de objetos alarmados

A lista de objeto será representada com por um array de objetos. Todos os objetos terão as mesmas proriedades. 
Os campos id_alarm e id_object são numéricos representando identificadores para os objetos.
Os campos start e end são timestamps no formato Unix timestamp.
A propriedade end só estará preenchida caso um objeto esteja desalarmado.
Os campos alarm_name e object_name são textuais e representam os nomes do alarm e do objeto.
O campo type poderá ter os seguintes valores: Dispositivo e Interface.
O campo id_priority é numérico e faz referência a outro array (Lista de prioridades) que srá descrito abaixo.

```
[
  {  
    id_alarm: <id_alarm>,
    id_object: <id_object>,
    start: <unix_timestamp>,
    end: [unix_timestamp],
    id_priority: <id_priority>,
    alarm_name: <alarm_name>,
    object_name: <object_name>,
    type: <type>
  },
  ...
  {  
    id_alarm: <id_alarm>,
    id_object: <id_object>,
    start: <timestamp_epoch_time>,
    end: [timestamp_epoch_time],
    id_priority: <id_priority>,
    name: <name>,
    type: <type>
  }
]
```
  
### Lista de prioridades

A lista de prioridades será usada para colorir as linhas da lista de objetos da tela inicial.
A lista de prioridades será representada por um array associativo. 

```
{
  0:
    {
      name: 'Normal',
      text_color: '#fff',
      background_color: '#0f0',
      priority: 0
    },
  1:
    {
      name: 'Level 1',
      text_color: '#fff',
      background_color: #c00,
      priority: 1
    },
  2:
    {
      name: 'Level 2',
      text_color: '#fff',
      background_color: '#a0a000',
      priority: 2
    },
  3:
    {
      name: 'Level 3',
      text_color: '#fff',
      background_color: '#d7d700',
      priority: 3
    },
}
```

### Exibindo a lista

A tela inicial deve exibir o conteúdo da lista de objeto, ordenado de forma decrescente pelo 'start_time' e colorindo as linhas de acordo com os valores informados na lista de prioridades.

Cada item na linha deve ser selecionável. Ao selecionar um item da lista, o aplicativo deve direcionar a tela para um gráfico com o nome do objeto selecionado.
Este gráfico deverá representar um período diário, exibindo como horário final o horário corrente, normalizado por 5 minutos, e o horário inicial 24 horas atrás.
Exemplo: horário inicial: 03/08/2020 12:00 - Horário final: 04/08/2020 11:55.
O gráfico deverá ter 288 pontos, representando pontos de 5 minutos.
O gráfico deverá ter 2 curvas: Entrada e Saída. A curva de entrada deverá ser na cor azul e saída na cor verde.
Os dados podem ser gerados aleatoriamente ou podem ser fixos, ficando ao seu critério.

Nesta tela deverá ter uma opção para retornar a tela inicial com a lista de objetos alarmados.


## Instruções para entrega do projeto

- O projeto deverá ser feito usando React Native
- A entrega deve ter instruções de como executar o projeto para ser testado
- Você será avaliado pela diagramação e visual da sua solução, bem como as ténicas usadas para consumir as APIs e exibir os dados.
- Não economize no visual e na usabilidade.
- Desenvolva e use Git para versionamento do código
- Qualquer dúvida sobre esse projeto podem ser perguntadas por email em github@telcomanager.com
