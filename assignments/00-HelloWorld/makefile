all: clean run

clean:
	find build -mindepth 1 ! -name 'README.txt' -delete && clear
compile:
	cd build && cmake -DMAIN_EXECUTABLE=ON .. && cmake --build . && clear && cd ..
run: compile
	cd build && ./exercise && cd ..
debug: 
	cd build && cmake -DVISUAL_STUDIO_DEBUG_NORMAL=ON .. && cmake --build . && clear && cd ..
	gdb build/dexercise
	clear
debugvs:
	cd build && cmake -DVISUAL_STUDIO_DEBUG_NORMAL=ON .. && cmake --build . && clear && echo "Lista la compilación para depuración. Abra el programa principal e inicie la depuración de pruebas de VS Code..." && cd ..