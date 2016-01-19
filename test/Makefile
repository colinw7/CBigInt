CC = g++
RM = rm

CDEBUG = -g
LDEBUG = -g

INC_DIR = ../include
OBJ_DIR = .
LIB_DIR = ../lib
BIN_DIR = ../bin

all: $(BIN_DIR)/CBigIntTest

SRC = \
CBigIntTest.cpp

OBJS = $(patsubst %.cpp,$(OBJ_DIR)/%.o,$(SRC))

CPPFLAGS = \
-std=c++11 \
-I$(INC_DIR) \
-I../../CStrUtil/include \
-I../../CUtil/include \
-I.

LFLAGS = \
-L$(LIB_DIR) \
-L../../CStrUtil/lib \

LIBS = \
-lCBigInt \
-lCStrUtil \

clean:
	$(RM) -f $(OBJ_DIR)/*.o
	$(RM) -f $(BIN_DIR)/CBigIntTest

.SUFFIXES: .cpp

.cpp.o:
	$(CC) -c $< -o $(OBJ_DIR)/$*.o $(CPPFLAGS)

$(BIN_DIR)/CBigIntTest: $(OBJS) $(LIB_DIR)/libCBigInt.a
	$(CC) $(LDEBUG) -o $(BIN_DIR)/CBigIntTest $(OBJS) $(LFLAGS) $(LIBS)
