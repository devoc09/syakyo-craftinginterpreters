# Makefile for building a single directory of Java source files. It requires
# a DIR variable to be set.

BUILD_DIR := build

SOURCES := $(wildcard *.java)
CLASSES := $(SOURCES:.java=.class)

JAVA_OPTIONS := -Werror

default: build_all

# Compile a single .java file to .class.
build_all: $(SOURCES)
	@ mkdir -p $(BUILD_DIR)
	@ javac -cp . -d $(BUILD_DIR) $(JAVA_OPTIONS) -implicit:none $(SOURCES)
	@ printf "%8s %-60s %s\n" javac "$(SOURCES)" "$(JAVA_OPTIONS)"

execLox:
	java -cp build com.craftinginterpreters.lox.Lox

fmt:
	java -jar bin/google-java-format-1.18.1-all-deps.jar --replace *.java

generateAST:
	javac -cp . -d tool -Werror tool/GenerateAst.java

execGenerateAST:
	rm -f tool/ast/Expr.java && java -cp tool com.craftinginterpreters.tool.GenerateAst tool/ast



.PHONY: default build_all
