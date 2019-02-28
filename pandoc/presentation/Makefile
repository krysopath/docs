BUILD_DIR ?= .
PROJECT_NAME := $(shell basename $(realpath .))

$(PROJECT_NAME).pdf: presentation.md logo.png
	pandoc -t beamer -o $(BUILD_DIR)/$@ $<

