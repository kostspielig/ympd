.PHONY: all data sass serve

all: data sass cljs

#
# Dependencies
# ============
#

prepare:
	npm install
	$(MAKE) all

#
# Development
# ===========
#

DATA =  resources/data/data.json

resources/%.json: %.yaml
	mkdir -p $(@D)
	python -c 'import sys, yaml, json; \
		   json.dump(yaml.load(sys.stdin), sys.stdout, indent=4)' \
		< $< > $@

data: $(DATA)

sass:
	compass compile

cljs:
	lein cljsbuild once

figwheel:
	rlwrap lein figwheel

COFFEE = node_modules/coffee-script/bin/coffee
serve:
	$(COFFEE) server.coffee

# pip install watchdog
watch-data:
	watchmedo shell-command \
		--recursive \
		--command="$(MAKE) data" \
		data/

watch-sass:
	compass watch

watch-cljs:
	lein cljsbuild auto debug

dev:
	trap "trap - TERM && kill 0" EXIT TERM INT; \
	$(MAKE) watch-data & \
	$(MAKE) watch-sass & \
	$(MAKE) serve & \
	$(MAKE) figwheel


#
# Deployment
# ==========
#

upload:
	@echo "deployment not implemented"
