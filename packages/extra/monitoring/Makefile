NAME=monitoring

include ../../../scripts/package.mk

generate:
	readme-generator -v values.yaml -s values.schema.json.tmp -r README.md
	cat values.schema.json.tmp | \
		jq '.properties.metricsStorages.items.type = "object" | .properties.logsStorages.items.type = "object"' \
		> values.schema.json
	rm -f values.schema.json.tmp
