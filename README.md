# stm32-ppm

Modulação por Posição de Pulso (PPM) com sincronismo externo no STM32F4xx.

## Descrição

Implementação de PPM (Pulse Position Modulation) usando timers do STM32 com sincronismo externo. PPM é uma técnica de modulação utilizada em sistemas de rádio controle e comunicação serial que codifica informação na posição temporal dos pulsos.

## Hardware

- Microcontrolador: STM32F4xx

## Periféricos utilizados

| Periférico | Função |
|------------|--------|
| TIM (timer) | Geração e medição de pulsos PPM |
| GPIO | Saída/entrada do sinal |
| USART2 | Debug serial |

## Conceito PPM

```
|← período →|← período →|← período →|
  ↑ pulso      ↑ posição = dado codificado
```

A posição do pulso dentro de um período fixo determina o valor transmitido.

## Estrutura

```
PPM/
├── Src/
│   ├── main.c
│   ├── tim.c / gpio.c
│   └── stm32f4xx_it.c
├── Inc/
└── Drivers/
```

## IDE

Atollic TrueSTUDIO 9.3 / STM32CubeIDE

## Autor

Prof. Marcos Zuccolotto — Centro Tecnológico Liberato
