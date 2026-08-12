MANUAL DO USUÁRIO E GUIA DE INSTALAÇÃO 
VU S-METER DIGITAL UNIVERSAL OLED
Engenharia de Software & Hardware: ( PU8AAT - flaviohat@gmail.com )
Base compativel S-Meter Digital: (WLG) ( https://kitdds.blogspot.com/ )
Edição Atualizada e Consolidada: 11/08/2026

1. INTRODUÇÃO E TECNOLOGIA UNDER THE HOOD.
Você tem em mãos o VU S-Meter digital mais rápido e fluido já desenvolvido para a comunidade de Rádio Cidadão (PX) e Radioamadorismo. Este equipamento foi projetado para ser 100% compatível com a pinagem e o circuito eletrônico da base do “Mestre Wander Lúcio Gomes (WLG)” (Acesse o blog oficial ( https://kitdds.blogspot.com/ )), desenvolvedor oficial deste e de muitos outros projetos fantásticos aqui no Brasil. Se você já possui o hardware dele instalado no seu Cobra 148GTL ou similar, a atualização é puramente via software (cabo USB), sem necessidade de alterar uma única solda ou resistor.
Para alcançar o movimento simulado digitalmente no mini Display OLED SSD1306 de 0,91 polegadas (128x32 pixels), o software extrai 100% da capacidade do processador ATmega328P (Arduino Nano) através de pilares de engenharia gráfica e eletrônica:
Modo Turbo I2C (400kHz): A velocidade de comunicação entre o chip e o display OLED foi quadruplicada em relação ao padrão de mercado (100kHz). Isso eleva a taxa de atualização para 60 FPS (Quadros por Segundo), eliminando qualquer atraso visual (delay).
Super-Amostragem Digital (Oversampling 16x / 4x): A cada ciclo de exibição, o processador colhe 16 amostras analógicas ultra-rápidas do pino de sinal e 4 amostras do voltímetro. Essa técnica purifica a leitura, elimina ruídos elétricos gerados pela transmissão do rádio e garante estabilidade absoluta.
Resolução Virtual de 512 Níveis: Através de mapeamento decimal (ponto flutuante), o ponteiro não pula de pixel em pixel. Ele se desloca em frações milimétricas, entregando a balística idêntica à de um galvanômetro analógico mecânico de bobina móvel.
Anti-Aliasing por Densidade Vertical (Dither Dinâmico): Simula tons de cinza reais em uma tela estritamente monocromática. Enquanto a frente do ponteiro preenche os pixels na vertical de forma diretamente proporcional ao movimento, o rastro desvanece de forma inversamente proporcional, mantendo a massa visual e o foco da luz estáveis, sem oscilações em repouso. Ele agora opera liberado desde o pixel zero da tela.
Peak Hold Inteligente de 1 Segundo: O retentor de pico segura o marcador no topo por exatos 1000ms. Um tempo calculado cientificamente para respeitar a velocidade de assimilação do cérebro humano, permitindo registrar a modulação máxima sem pressa antes da descida lenta.

2. PRIMEIROS PASSOS: O PROCEDIMENTO DE CALIBRAÇÃO OBRIGATÓRIA

(A calibração do voltímetro deve ser o primeiro passo após fixar o hardware e instalar a Firmware no equipamento. O fator de correção é gravado em uma célula isolada da memória EEPROM, o que significa que ele nunca mais se perderá, mesmo que você atualize ou reinstale o firmware no futuro).
Passo a Passo para Calibração de Precisão:
1. Conexão de Tensão: Injete uma tensão de exatos 12.0 Volts DC estabilizados na entrada de alimentação no rádio com o VU S-Meter Digital devidamente instalado.
2. Iniciando o Modo de Aferição: Com o rádio desligado, mantenha o botão de seleção (Pino A3) pressionado e ligue o rádio.
3. Sequência Visual do Boot:
O visor exibirá a tela oficial de apresentação por 3 segundos.
Em seguida, a tela mudará para o letreiro: "MODO CALIBRAÇÃO" na primeira linha.
4. Gravando na Memória: Mantenha o botão pressionado. No exato momento em que você soltar o botão, o processador calculará a média matemática das amostras, salvará o fator de correção na EEPROM e exibirá na segunda linha a mensagem: "CALIBRAÇÃO OK!".
5. Inicialização: Após 2 segundos exibindo o sucesso, o visor limpará o buffer automaticamente e entrará direto no VU Analógico Digital - 01 com precisão de laboratório.
3. GUIA DE COMANDOS DO USUÁRIO
Clique Curto (Toque Rápido): Alterna ciclicamente entre os 14 modos gráficos de exibição (Modos 0 a 13).
Clique Longo (Pressionar por mais de 600ms): Entra no ajuste de brilho progressivo. Enquanto você mantiver o botão pressionado, o visor alternará entre os 5 níveis de brilho digital a cada 500ms. Ao atingir o brilho desejado, basta soltar o botão. O visor piscará em modo invertido para confirmar que o nível foi gravado permanentemente na EEPROM (o rádio ligará sempre no brilho escolhido).
4. DESCRIÇÃO DOS 14 MODOS GRÁFICOS.
VU-01: Ponteiro Analógico de Elite (Dither Dinâmico, High-contrast VU meter)
A tela principal foi pensada em um melhor contraste visual fundo    ponteiro na escala clássica de S-Meter de rádio PX, um ponteiro balístico robusto. Movimento ultra-suave e responsivo com fumaça gráfica nas bordas durante o deslocamento e fixação sólida quando em repouso.

VU-02: Super Bargraph Horizontal com Pico (Peak Hold)
Uma barra horizontal de preenchimento rápido que ocupa toda a altura útil de medição. Possui um marcador de pico flutuante que congela por 1 segundo no topo e desce suavemente, ideal para monitoramento de modulação em ambientes de laboratório ou competições.
VU-03: Barra Horizontal Clássica
Design elegante e minimalista. Uma barra horizontal compacta centralizada na tela com leitura precisa e marcador de pico integrado, mantendo a escala de SWR/CAL visível no topo.


VU-04: Bloquinho Central Flutuante (Segmentado)
Neste modo, a barra não se preenche desde o início. Um bloco de leitura se desloca flutuando ao longo da escala horizontal, indicando o ponto exato da força de sinal atual como se fosse um cursor de precisão.

VU-05: LEDs Sólidos Virtuais
Simula os clássicos painéis de VUs de LEDs dos equipamentos de som dos anos 80 e 90. São 10 blocos horizontais robustos que acendem de forma cheia e imediata conforme o sinal avança.

VU-06: LEDs Virtuais com Retenção de Pico
Mesma estética de blocos segmentados do VU-05, porém adiciona o recurso de retenção: o último bloco atingido fica aceso de forma independente por 1 segundo antes de retornar, registrando graficamente os picos de transmissão.

VU-07: LEDs Virtuais em Escada (Gráfico de Barra Vertical)
Os blocos ganham altura progressiva da esquerda para a direita, formando uma escada de indicação com o letreiro "SIG" destacado em fonte ampliada para facilitar a visualização rápida no painel do rádio.

VU-08: LEDs em Escada com Retenção de Pico
Une a imponência visual da escada com fonte ampliada do VU-07 ao filtro de retenção de pico de 1000ms, entregando um mapeamento dinâmico e estético para a estação.

VU-09: S-Meter Digital Gigante (Leitura em dB)
Focado na leitura puramente numérica e direta. Exibe na tela central, em tamanho gigante, a indicação exata do nível de sinal (ex: S-5 ou S9+30dB), eliminando erros de interpretação visual.

VU-10: Osciloscópio de Sinal / Modulação em Tempo Real
Transforma a sua tela OLED em um analisador de formas de onda. Ele plota o gráfico de variação contínua do sinal de entrada em uma linha de varredura horizontal, permitindo "enxergar" o desenho da sua própria voz ou da recepção.

VU-11: Voltímetro de Ponteiro Analógico (Single)
Visual clássico de painel automotivo de luxo. Possui o letreiro "TENSAO DA FONTE DC" fixado de forma limpa no topo e uma régua centralizada de alta precisão para os Volts inteiros (10v a 14v) e traços para as frações de 250mV. Resposta balística pesada com filtro contra trepidações, gerando um movimento majestoso.

VU-12: Voltímetro DC Digital de Precisão
Monitore a saúde da fonte de alimentação da sua estação de forma puramente numérica. Exibe em letras garrafais a voltagem da linha DC (ex: 13.8 Volts) com filtros de suavização digitais lentos, que impedem que a leitura fique tremendo na tela.

VU-13: VU Coaxial de Ponteiro Duplo Simultâneo (Inovação Exclusiva)
O ápice técnico do projeto. A tela é dividida ao meio por uma linha central horizontal delimitada por batentes verticais. A metade superior mostra o Voltímetro Analógico com escala fracionada a cada 500mV. A metade inferior traz o S-Meter Analógico com a escala de dB completa (+10, +20 e +30dB cravados). Dois ponteiros independentes e com respostas balísticas diferentes cruzam a tela ao mesmo tempo!

CICLO-14 Tela de Info / Créditos Finais
A assinatura de autenticidade e o encerramento do ciclo. Exibe o layout oficial de três linhas: VU S-METER UNIVERSAL, o selo de versão PU8AAT-ver. 11/08/26 e a chancela de engenharia reversa e compatibilidade Base Compat. (WLG).Nota: Quando selecionado manualmente no botão, este modo permanece ativo por 2 segundos e retorna automaticamente ao VU-01.
5. CRÉDITOS E DIRETRIZES DE DISTRIBUIÇÃO GRATUITA
Este software é um esforço de desenvolvimento e evolução voluntário iniciado por Flávio Henrique (PU8AAT) 100% compativel ao esquema de ligações eletrônica do projeto (WLG), ( https://kitdds.blogspot.com/ ) facilitando assim a atualização dessa nova Firmware em equipamentos que já o possuem.

PROJETO DE DISTRIBUIÇÃO GRATUITA: 
Fica terminantemente proibida a venda, comercialização ou restrição de acesso a essa Firmware e manual. Ela foi projetada para elevar o nível tecnológico do radioamadorismo mundial de forma acessível e gratuita.

Dica de um mini Arduino com entrada USB-C para montagem do VU.

 Forte 73 de PU8AAT! Bons contatos e excelente modulação!
