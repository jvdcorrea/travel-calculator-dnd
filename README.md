Para usar [clique aqui](https://jvdcorrea.github.io/travel-calculator-dnd/)

# ⚔ D&D 5e: Planejador de Viagens

Calculadora de viagem para D&D 5e (regras de 2014) que roda direto no navegador. Carregue o mapa da sua campanha, defina a escala, trace a rota e veja quanto tempo o grupo leva para chegar, de acordo com o ritmo, o meio de transporte e as horas de viagem por dia.

É um único arquivo HTML, sem dependências, sem servidor e sem instalação.

<!-- Adicione aqui um print da ferramenta: ![Planejador de Viagens](docs/screenshot.png) -->

## Funcionalidades

- **Ritmos do Livro do Jogador** (lento, normal e rápido), com os efeitos de cada um em Percepção, furtividade, navegação e forrageio.
- **Marcha forçada:** ao passar de 8 horas por dia, mostra as salvaguardas de Constituição necessárias e a CD de cada hora extra.
- **Terreno difícil:** reduz a distância pela metade (voo e veículos de velocidade fixa ignoram).
- **Vários meios de transporte:** terrestre pelo Livro do Jogador, terrestre e voo pelo ritmo especial do Guia do Mestre, embarcações e aeronave, com valores de referência do livro.
- **Mapa interativo:** zoom com a roda do mouse ou pinça, arrastar para mover e renderização na resolução real da tela.
- **Escala flexível:** calibre marcando dois pontos de distância conhecida ou digite a escala diretamente. Uma barra de escala no canto do mapa acompanha o zoom.
- **Rota com vários pontos:** marque início, curvas e destino; a distância é somada trecho a trecho.
- **Mapas salvos no navegador:** imagem, escala e rota ficam guardados, e o último mapa usado abre sozinho.
- **Exportar e importar** mapas em `.json` para backup ou para passar à mesa.
- **Milhas ou quilômetros**, e deslocamento em pés ou metros.

## Como usar

### Abrindo a ferramenta

Baixe o `calculadora_viagem_dnd.html` e abra no navegador. Também dá para publicar no GitHub Pages: renomeie o arquivo para `index.html`, ative o Pages nas configurações do repositório e acesse pelo link gerado.

### Passo a passo

1. **Unidades:** escolha milhas ou quilômetros, e pés ou metros.
2. **Ritmo:** escolha o ritmo, as horas de viagem por dia e, se for o caso, marque terreno difícil.
3. **Transporte:** escolha o tipo e, se quiser, uma referência do livro (ex.: cavalo de montaria, pégaso, galé).
4. **Mapa:** carregue uma imagem (PNG, JPG ou WebP).
5. **Escala:** informe a distância real e clique em *Marcar 2 pontos*, ou digite a escala em pixels por milha (ou por km).
6. **Rota:** clique em *Desenhar rota* e marque os pontos no mapa. Clique de novo no botão ou aperte Esc para terminar.
7. **Salvar:** dê um nome ao mapa e clique em *Salvar*. A partir daí, mudanças na escala e na rota são salvas automaticamente.

### Compartilhando a escala com a mesa

A escala é medida em pixels da imagem original. Depois de calibrar, o campo de escala manual mostra o valor (ex.: `1 milha = 25,4 px`). Passe esse número para os outros jogadores e eles digitam no mesmo campo. Para funcionar, todos precisam usar o mesmo arquivo de imagem; a ferramenta mostra a resolução da imagem para conferir.

Outra opção é exportar o mapa em `.json`, que inclui imagem, escala e rota, e enviar o arquivo.

## Regras implementadas

### Ritmo de viagem (Livro do Jogador, cap. 8)

| Ritmo  | Por hora | Por dia (8 h) | Efeitos |
|--------|----------|---------------|---------|
| Rápido | 4 milhas | 30 milhas     | −5 na Sabedoria (Percepção) passiva; −5 no teste do navegador; não dá para forragear |
| Normal | 3 milhas | 24 milhas     | Nenhum |
| Lento  | 2 milhas | 18 milhas     | Pode se mover furtivamente; +5 no teste do navegador |

Os efeitos de navegação e forrageio vêm do Guia do Mestre (cap. 5). Pela regra padrão, o ritmo do grupo não depende do deslocamento individual de cada personagem.

### Marcha forçada

O padrão é 8 horas de viagem por dia. Ao fim de cada hora extra, cada personagem faz uma salvaguarda de Constituição com CD 10 + 1 por hora além de 8. Cada falha causa um nível de exaustão.

### Tipos de transporte

| Tipo | Como calcula |
|------|--------------|
| Terrestre (PHB) | Ritmo do Livro do Jogador × multiplicador (1 = regra oficial; outros valores são regra da casa) |
| Terrestre (DMG) | Deslocamento em pés ÷ 10 = milhas por hora, ajustado pelo ritmo |
| Voo (DMG) | Igual ao anterior; ignora terreno difícil |
| Embarcação | Velocidade fixa do navio; o ritmo não se aplica |
| Aeronave | Velocidade fixa (8 mi/h no Guia do Mestre); o ritmo não se aplica |

No ritmo especial do Guia do Mestre, o ritmo rápido soma 1/3 à velocidade e o lento multiplica por 2/3. Pela letra da regra, ele vale para deslocamento de voo ou concedido por magia, motor ou força natural. Usá-lo para montarias terrestres comuns é uma extensão que muitas mesas adotam.

### Unidades

O modo em quilômetros segue a convenção do livro em português: 1 milha = 1,5 km e 5 ft = 1,5 m. Por isso o ritmo normal aparece como 4,5 km/h e 36 km por dia.

## Armazenamento

Os mapas ficam salvos no **IndexedDB** do navegador, que comporta imagens grandes. Os dados ficam só na sua máquina, nesse navegador. Por isso:

- Limpar os dados do navegador apaga os mapas salvos. Use *Exportar mapa* para ter um backup.
- Mapas salvos num navegador não aparecem em outro. Use exportar e importar para levar de um para o outro.
- Alguns navegadores bloqueiam o armazenamento quando o HTML é aberto direto do disco (o Safari, por exemplo). Nesse caso, publique no GitHub Pages ou use exportar e importar.

## Limitações conhecidas

- A distância é medida em linha reta entre os pontos da rota. Para seguir estradas e rios, marque mais pontos nas curvas.
- A ferramenta não modela terreno por trecho da rota; terreno difícil vale para a viagem inteira.
- As regras não dizem se montarias também fazem a salvaguarda de marcha forçada; fica a critério do mestre.
- Considera apenas as regras de 2014. As regras de 2024 tratam viagem de forma diferente.

## Licença

Defina a licença do projeto (por exemplo, MIT) e adicione um arquivo `LICENSE` ao repositório.

D&D e Dungeons & Dragons são marcas da Wizards of the Coast. Este é um projeto de fã, sem afiliação oficial.
