MANUAL DO USUÁRIO E GUIA DE INSTALAÇÃO 
VU S-METER DIGITAL UNIVERSAL OLED
Engenharia de Software & Hardware: ( PU8AAT - flaviohat@gmail.com )


INTRODUÇÃO E TECNOLOGIA UNDER THE HOOD.
Você tem em mãos o VU S-Meter digital mais rápido e fluido já desenvolvido para a comunidade de Rádio Cidadão (PX) e Radioamadorismo. Este equipamento foi projetado para ser 100% compatível com a pinagem e o circuito eletrônico da base do “Mestre Wander Lúcio Gomes (WLG)” (Acesse o blog oficial ( https://kitdds.blogspot.com/ )), desenvolvedor oficial deste e de muitos outros projetos fantásticos aqui no Brasil. Se você já possui o hardware dele instalado no seu Cobra 148GTL ou similar, a atualização é puramente via software (cabo USB), sem necessidade de alterar uma única solda ou resistor.
Para alcançar o movimento simulado digitalmente no mini Display OLED SSD1306 de 0,91 polegadas (128x32 pixels), o software extrai 100% da capacidade do processador ATmega328P (Arduino Nano) através de pilares de engenharia gráfica e eletrônica:
Modo Turbo I2C (400kHz): A velocidade de comunicação entre o chip e o display OLED foi quadruplicada em relação ao padrão de mercado (100kHz). Isso eleva a taxa de atualização para 60 FPS (Quadros por Segundo), eliminando qualquer atraso visual (delay).
Super-Amostragem Digital (Oversampling 16x / 4x): A cada ciclo de exibição, o processador colhe 16 amostras analógicas ultra-rápidas do pino de sinal e 4 amostras do voltímetro. Essa técnica purifica a leitura, elimina ruídos elétricos gerados pela transmissão do rádio e garante estabilidade absoluta.
Resolução Virtual de 512 Níveis: Através de mapeamento decimal (ponto flutuante), o ponteiro não pula de pixel em pixel. Ele se desloca em frações milimétricas, entregando a balística idêntica à de um galvanômetro analógico mecânico de bobina móvel.
Anti-Aliasing por Densidade Vertical (Dither Dinâmico): Simula tons de cinza reais em uma tela estritamente monocromática. Enquanto a frente do ponteiro preenche os pixels na vertical de forma diretamente proporcional ao movimento, o rastro desvanece de forma inversamente proporcional, mantendo a massa visual e o foco da luz estáveis, sem oscilações em repouso. Ele agora opera liberado desde o pixel zero da tela.
Peak Hold Inteligente de 1 Segundo: O retentor de pico segura o marcador no topo por exatos 1000ms. Um tempo calculado cientificamente para respeitar a velocidade de assimilação do cérebro humano, permitindo registrar a modulação máxima sem pressa antes da descida lenta.

