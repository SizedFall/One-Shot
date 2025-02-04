# Sistema de Temporização para Acionamento de LEDs com Raspberry Pi Pico W

## Descrição
Este projeto implementa um sistema de temporização para o acionamento de LEDs utilizando o microcontrolador Raspberry Pi Pico W. Os LEDs são acionados por um botão (pushbutton) e desligam em etapas com um atraso de 3 segundos entre cada estado, utilizando a função `add_alarm_in_ms()` do Pico SDK.

## Requisitos
- Microcontrolador Raspberry Pi Pico W
- 3 LEDs (azul, vermelho e verde)
- 3 resistores de 330 Ω
- 1 botão (pushbutton)
- Ferramenta de simulação Wokwi
- Ferramenta Educacional BitDogLab
- Pico SDK configurado no ambiente de desenvolvimento

## Funcionamento
1. O sistema inicia aguardando o pressionamento do botão.
2. Ao pressionar o botão:
   - Todos os LEDs são ligados simultaneamente.
   - Após 3 segundos, um LED é desligado.
   - Após mais 3 segundos, o segundo LED é desligado.
   - Após mais 3 segundos, o último LED é desligado e o sistema retorna ao estado inicial.
3. Durante a sequência de temporização, o botão é bloqueado para evitar novas ativações.

## Configuração dos GPIOs
- **LED Azul** - GPIO 2
- **LED Vermelho** - GPIO 3
- **LED Verde** - GPIO 4
- **Botão (Pushbutton)** - GPIO 5
- **LED RGB (BitDogLab)** - GPIOs 11, 12 e 13

## Compilando e Executando
1. Configure o ambiente de desenvolvimento para o Raspberry Pi Pico W com o Pico SDK.
2. Compile o código utilizando `cmake` e `make`.
3. Carregue o binário gerado no Raspberry Pi Pico W.
4. Conecte ao dispositivo via porta serial para visualizar as mensagens de depuração.

## Simulação no Wokwi
Para simular o circuito no Wokwi:
1. Configure os LEDs, resistores e botão conforme a Figura 2 do enunciado.
2. Utilize o código fornecido e execute a simulação.

## Testes com BitDogLab
- Utilize os GPIOs 11, 12 e 13 para controlar um LED RGB.
- Utilize o Botão A (GPIO 5) para acionar o sistema.

## Opcional: Implementação de Debounce
- Pode ser adicionada uma rotina de debounce por software para evitar acionamentos falsos do botão.
