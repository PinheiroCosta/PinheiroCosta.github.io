+++
title = "Termostato"
date = 2021-06-10
description = "Algoritmo para um termostato que converte a temperatura de fahrenheit em celsius e vice versa."

[taxonomies]
categories = ["Relatos"]
tags = ["Termostato", "Algoritmo", "Javascript", "Python", "C"]

[extra]
image = ""
author = "Rômulo"
+++

# Termostato

## Javascript
```Javascript
class Termostato {
  constructor(fahrenheit) {
    this.fahrenheit = fahrenheit;
  }

  set temperatura(celsius){
    // converte temperatura em celsius para farenheit
    const C = celsius;
    const F = (C * 9.0) / 5 + 32;
    this.fahrenheit = F;
  }

  get temperatura() {
    // retorna temperatura em celsius
    const F = this.fahrenheit;
    const C = (5 / 9) * (F - 32);
    return C;

  }

}

const rj = new Termostato(95); 
let hoje = rj.temperatura; // 35 em Celsius
rj.temperatura = 26;
let ontem = rj.temperatura; // 26 em Celsius
```
