all:
	ln -fs /usr/share/radare2/last/www/t/r2.js
	node test.js

indent: node_modules/jsfmt
	node_modules/.bin/jsfmt -w index.js
	node_modules/.bin/jsfmt -w test.js

node_modules/jsfmt:
	mkdir -p node_modules
	npm install jsfmt

MODVER=$(shell node -e 'console.log(JSON.parse(require("fs").readFileSync("package.json"))["version"])')

npm publish:
	${MAKE}
	npm publish

unpublish:
	${MAKE}
	npm unpublish @${MODVER}
