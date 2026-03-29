# STM32 PPM — Modulação por Posição de Pulso

🇧🇷 **Português** | 🇺🇸 [English](#english)

---

## Português

Geração e captura de sinal PPM (Pulse Position Modulation) no STM32F4xx usando TIM3 com ETR externo e saída de comparação (OC).

### O que faz
- **TIM3** configurado com PSC=1953 e ARR=358
- Entrada ETR em **PD2** sincroniza o timer com sinal externo
- Saída de comparação em **PA6** gera pulsos PPM
- Alterna entre posições de **100** e **110** ticks (resolução de posição)

### Configuração do Timer
```
TIM3: PSC = 1953, ARR = 358
Clock do timer = 84 MHz / 1954 ≈ 43 kHz
Período = 43 kHz / 358 ≈ 120 Hz (ciclo PPM)
Posições: 100 ticks e 110 ticks
```

### Mapa de pinos
| Pino | Função |
|---|---|
| PD2 | ETR — entrada de sincronização externa |
| PA6 | TIM3 CH1 — saída PPM |

### Aplicação
PPM é usado em controle de servos e rádio controle (RC). Cada pulso codifica a posição do servo pelo seu tempo relativo ao pulso de sincronização.

### Microcontrolador
STM32F4xx — Atollic TrueSTUDIO

---

## English

PPM (Pulse Position Modulation) generation and capture on STM32F4xx using TIM3 with external ETR and output compare (OC).

### What it does
- **TIM3** configured with PSC=1953 and ARR=358
- ETR input on **PD2** synchronizes the timer with an external signal
- Output compare on **PA6** generates PPM pulses
- Alternates between positions of **100** and **110** ticks

### Timer configuration
```
TIM3: PSC = 1953, ARR = 358
Timer clock = 84 MHz / 1954 ≈ 43 kHz
Period = 43 kHz / 358 ≈ 120 Hz (PPM cycle)
Positions: 100 ticks and 110 ticks
```

### Pin map
| Pin | Function |
|---|---|
| PD2 | ETR — external sync input |
| PA6 | TIM3 CH1 — PPM output |

### Application
PPM is used in servo control and radio control (RC). Each pulse encodes the servo position by its timing relative to the sync pulse.

### MCU
STM32F4xx — Atollic TrueSTUDIO
