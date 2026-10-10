
Aplicação em C/C++ para detetar, rastrear e contar laranjas num vídeo. O programa utiliza a biblioteca OpenCV para ler e mostrar os frames, e funções próprias (vc.c/vc.h) para a segmentação e análise das imagens (blobs).

Principais Funcionalidades

Segmentação: Isola os objetos alaranjados no espaço de cores HSV e aplica operações morfológicas para reduzir o ruído visual.

Filtros: Filtra os objetos (blobs) detetados através da sua área, calibre, deformação, preenchimento e circularidade.

Rastreio e Contagem: Acompanha as laranjas ao longo dos frames e soma à contagem final sempre que uma laranja atravessa a linha horizontal (colocada a 65% da altura do ecrã do vídeo).

Visualização: Mostra diretamente na janela o identificador, as medidas, a categoria, o número de laranjas que estão no frame atual e o total já contabilizado.

O que precisas para correr o projeto (Requisitos) 

Sistema: Windows e Visual Studio 2022 (com a plataforma de ferramentas C++ v143).

OpenCV: Versão 4.13 instalada e configurada no projeto.

Nota: As definições atuais do ficheiro .vcxproj estão a apontar para caminhos locais (como C:\opencv\build) e para a biblioteca opencv_world4130 (ou opencv_world4130d no modo Debug). Se tiveres o OpenCV noutra pasta, vais ter de ajustar isto!

Passo a Passo: Compilação e Execução 

Abre a solução: Dá duplo clique no ficheiro VC-GY.sln para abrir no Visual Studio.

Configura o OpenCV: Se necessário, vai às propriedades do projeto e ajusta os caminhos de inclusão (include) e das bibliotecas (lib) do OpenCV para os da tua máquina.

Compila: Seleciona a arquitetura x64 e o modo de configuração Debug ou Release. A seguir, compila e arranca com o projeto.

Encontra o vídeo: O ficheiro executável vai procurar o video.avi na pasta de trabalho atual. O repositório já traz este vídeo (VC-GY/video.avi). O ideal é configurares a pasta de trabalho nas opções para VC-GY ou, se preferires, copiares simplesmente o vídeo para a mesma pasta onde o teu executável vai parar.

Controlos de visualização: Carrega na tecla q na janela do vídeo se quiseres fechar o programa. O programa vai ficar à espera que carregues na tecla Enter na consola, tanto antes como depois do processamento, para te mostrar o tempo exato que demorou a correr.

Estrutura dos Ficheiros 

VC-GY/Source.cpp — Trata da leitura do vídeo, do rastreio, da contagem e da apresentação visual.

VC-GY/vc.c e VC-GY/vc.h — Têm a lógica das operações de imagem, a segmentação, a análise de blobs e a classificação.

VC-GY/video.avi — O vídeo de entrada (já incluído).

VC-GY/VC-GY.vcxproj e VC-GY.sln — Os ficheiros base que definem o projeto e a solução do Visual Studio.
