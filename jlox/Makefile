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

fmt:
	java -jar google-java-format-1.18.1-all-deps.jar --replace *.java


.PHONY: default build_all
