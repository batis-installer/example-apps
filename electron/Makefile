ELECTRON_VERSION := 0.34.3
VERSION := 0.1

# This will use electron-packager to get the specified version of Electron and
# copy files to the right places. Install this by running:
#   npm install -g electron-packager

batis: batis-electron-example-$(VERSION)-x86.app.tgz batis-electron-example-$(VERSION)-x86_64.app.tgz

batis-electron-example-$(VERSION)-x86.app.tgz: app_build_sentinel $(shell find batis_info)
	rm -rf build/batis-electron-example-linux-ia32/batis_info
	cp --archive batis_info build/batis-electron-example-linux-ia32/
	@echo "Packing for arch x86..."
	batis pack build/batis-electron-example-linux-ia32 -n batis-electron-example -o $@
	@echo "\"sha512\": \"$$(sha512sum $@ | cut -d' ' -f1)\""

batis-electron-example-$(VERSION)-x86_64.app.tgz: app_build_sentinel $(shell find batis_info)
	rm -rf build/batis-electron-example-linux-x64/batis_info
	cp --archive batis_info build/batis-electron-example-linux-x64/
	@echo "Packing for arch x86_64..."
	batis pack build/batis-electron-example-linux-x64 -n batis-electron-example -o $@
	@echo "\"sha512\": \"$$(sha512sum $@ | cut -d' ' -f1)\""

app_build_sentinel: $(shell find electron-quick-start)
	electron-packager electron-quick-start/ batis-electron-example --platform=linux \
		--arch=all --version=$(ELECTRON_VERSION) --out=build/
	touch $@

clean:
	rm -rf build app_build_sentinel

.PHONY: batis
