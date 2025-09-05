# Testes

# Nome do executável
TARGET = jogo

# Compilador
CXX = g++

# Flags de compilação
CXXFLAGS = -Wall -std=c++17

# Flags da SFML (gráficos, janela, sistema)
LIBS = -lsfml-graphics -lsfml-window -lsfml-system

# Arquivos fonte
SRC = main.cpp

# Arquivos objeto
OBJ = $(SRC:.cpp=.o)

# Regra padrão
all: $(TARGET)

# Compilar o executável
$(TARGET): $(OBJ)
	$(CXX) $(CXXFLAGS) -o $@ $^ $(LIBS)

# Executar
run: $(TARGET)
	./$(TARGET)

# Limpar arquivos objeto e executável
clean:
	rm -f $(OBJ) $(TARGET)
