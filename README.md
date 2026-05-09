# Vivencial 1 — Processamento Gráfico

Universidade do Vale do Rio dos Sinos — 2026/1

**Alunos:** João Carlos Fernandes Battassini e Kauan Scheffer Tedesco

---

## Descrição

Aplicação interativa em OpenGL que permite ao usuário desenhar triângulos na tela através de cliques do mouse. A cada três cliques, um triângulo é formado e preenchido com uma cor aleatória. Vértices pendentes são exibidos como pontos amarelos enquanto o triângulo ainda não está completo.

---

## Funcionalidades

- Clique com o botão esquerdo do mouse para adicionar vértices
- A cada 3 vértices, um triângulo é criado automaticamente com cor aleatória
- Vértices pendentes aparecem como pontos amarelos (8px)
- Múltiplos triângulos podem ser desenhados em sequência
- Projeção ortográfica com origem no centro da janela (1 unidade = 1 pixel)
- Pressione `ESC` para fechar a aplicação

---

## Estrutura do projeto

```
ExampleCode2/
├── ExampleCode/
│   ├── Source.cpp          
│   ├── glad.c             
│   ├── glfw3.dll           
│   ├── libgcc_s_seh-1.dll
│   ├── libstdc++-6.dll
│   ├── libwinpthread-1.dll
│   └── Source.exe          
├── Dependencies/
│   ├── GLAD/               
│   ├── glfw-3.4.bin.WIN64/ 
│   ├── glm/                
│   └── stb_image/          
├── Common/
│   ├── include/Shader.h
│   └── src/Shader.cpp
└── .vscode/
    ├── tasks.json          
    └── c_cpp_properties.json
```

---

## Requisitos

- Windows 64-bit
- [MSYS2](https://www.msys2.org/) com ambiente UCRT64
- Compilador `g++` do MinGW-w64

### Instalando o compilador (MSYS2 UCRT64)

Abra o terminal **MSYS2 UCRT64** e execute:

```bash
pacman -S mingw-w64-ucrt-x86_64-gcc
```

---

## Compilação

Abra o terminal na pasta raiz `ExampleCode2/` e execute:

```bash
g++ -g \
  -I./Dependencies/GLAD/include \
  -I./Dependencies/glfw-3.4.bin.WIN64/include \
  -I./Dependencies/glm \
  -I./Common/include \
  ./ExampleCode/Source.cpp \
  ./ExampleCode/glad.c \
  -L./Dependencies/glfw-3.4.bin.WIN64/lib-mingw-w64 \
  -lglfw3dll \
  -lopengl32 \
  -lgdi32 \
  -o ./ExampleCode/Source.exe
```

## Execução

Navegue até a pasta `ExampleCode/` e execute o binário:

```bash
cd ExampleCode2/ExampleCode
./Source.exe
```

As DLLs necessárias (`glfw3.dll`, `libstdc++-6.dll`, etc.) já estão incluídas na mesma pasta do executável.


