VERSION := $(shell python3 -c "import listapp; print(listapp.__version__)")

batis: ui
	rm -rf build/batis
	exit 0
	mkdir -p build/batis
	# Copy files into a build directory
	cp --archive listapp run.py batis_info build/batis/
	# Remove cached .pyc files
	rm -rf build/batis/listapp/__pycache__
	batis pack build/batis -n batis-pyqt-example -o batis-pyqt-example-$(VERSION).app.tgz
	@echo "\"sha512\": \"$$(sha512sum batis-pyqt-example-$(VERSION).app.tgz | cut -d' ' -f1)\""

ui: listapp/main.py

listapp/main.py: listapp/main.ui
	pyuic5 -o $@ $<
