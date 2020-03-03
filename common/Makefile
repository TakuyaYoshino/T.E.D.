COMPILER = g++ -std=c++17 -O3
INC_DIR  = ./include
SRC_DIR  = ./src
OBJ_DIR  = ./build
INCLUDE  = -I ${INC_DIR}
SOURCES  = $(shell ls $(SRC_DIR)/*.cpp) 
OBJS     = $(subst $(SRC_DIR),$(OBJ_DIR), $(SOURCES:.cpp=.o))
TARGET   = $(shell basename `pwd`)

all: $(TARGET)

$(TARGET): $(OBJS)
	$(COMPILER) -o $@ $(OBJS)

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.cpp 
	@if [ ! -d $(OBJ_DIR) ]; \
		then echo "mkdir -p $(OBJ_DIR)"; mkdir -p $(OBJ_DIR); \
	fi
	$(COMPILER) $(INCLUDE) -o $@ -c $< 

clean:
	rm -f $(OBJS) $(TARGET) $(SRC_DIR)/*~ $(INC_DIR)/*~

.PHONY: all clean
