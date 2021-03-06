---
layout: post
title: Como converter video em gif 
date: 2020-12-11
categories: Bash
published: true
---

Estava de boa aqui trabalhando no meu site, quando de repente o plugin da ferramenta que uso pra editar meus códigos mostrou um erro na tela. Resolvi então fazer uma pausa e reportar o bug no repositório dos desenvolvedores do plugin. Conforme eu preenchia o formulário, percebi que demonstrar o problema com um gif ao invés de vários screenshots seria mais eficiente.

A maneira mais conveniente que me veio em mente foi fazer um screencast com a ferramenta nativa do gnome, que pode ser ativada através do atalho `Ctrl` + `Alt` + `Shift` + `R`. Um círculo vermelho/laranja aparece no canto superior direito do monitor indicando que a tela está sendo gravada. Aí é só apertar `Ctrl` + `Alt` + `Shift` + `R` mais uma vez quando a gravação estiver concluída que a ferramenta joga a gravação no formatdo .webm direto na pasta 'Vídeos' do nosso sistema. Legal!

![gif](https://github.com/PinheiroCosta/PinheiroCosta.github.io/raw/master/_images/erro.gif)

Mas como infelizmente alguns sites não aceitam webm incorporados em suas páginas. Converter pra gif me pareceu uma boa opção.
Para isso utilizei a ferramenta [FFmpeg](https://ffmpeg.org/).

```shell 
$ ffmpeg -y -i "mywebmfile.webm" -vf palettegen "palette.png" 
```

> "-y" é aplicado para sobrescrever forçadamente o arquivo de destino, sem precisar da nossa confirmação.

> "-i" indica que o proximo parametro deve ser o arquivo de entrada (input), no nosso caso o arquivo webm.

> "-v" ativa o modo 'verborrágico' mostrando a saída de cada etapa do processo.

> "-f" força um formato de saída para o comando a ser executado, neste caso o formato png.
