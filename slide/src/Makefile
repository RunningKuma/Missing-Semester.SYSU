NPM_CACHE ?= /tmp/npm-cache
REVEAL_MD ?= env NPM_CONFIG_CACHE=$(NPM_CACHE) npx reveal-md
HOST ?= 127.0.0.1
PORT ?= 1948
COMMON_ARGS := --scripts https://cdn.tonycrane.cc/heti/heti.js,heti_worker.js --template template.html

.PHONY: live build clean

live:
	@echo "Previewing main slides on http://$(HOST):$(PORT)"
	@$(REVEAL_MD) main.md -w --disable-auto-open --host $(HOST) --port $(PORT) $(COMMON_ARGS)

build:
	@echo "Building main slides..."
	@$(REVEAL_MD) main.md $(COMMON_ARGS) --static ../site --assets-dir assets
	@rm ../site/main.html

clean:
	@echo "Cleaning up..."
	rm -rf ../site/
