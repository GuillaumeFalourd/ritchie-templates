# SH
BIN_FOLDER=bin
SH=$(BIN_FOLDER)/run.sh
BAT=$(BIN_FOLDER)/run.bat
BIN_NAME=main.ps1

build: bash-build sh-unix bat-windows docker

bash-build:
	mkdir -p $(BIN_FOLDER)
	cp -r src/* $(BIN_FOLDER)
	chmod +x $(BIN_FOLDER)/$(BINARY_NAME)

sh-unix:
	echo '#!/usr/bin/pwsh' > $(SH)
	echo './$(BIN_NAME)' >> $(SH)
	chmod +x $(SH)

bat-windows:
	echo '@ECHO OFF' > $(BAT)
	echo 'SET mypath=%~dp0' >> $(BAT)
	echo 'start /B /WAIT %mypath:~0,-1%/$(BIN_NAME)' >> $(BAT)

docker:
	cp Dockerfile set_umask.sh $(BIN_FOLDER)
