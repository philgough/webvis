TOPOJSON = node_modules/.bin/topojson
TOPOMERGE = node_modules/.bin/topojson-merge

all:

#
# Statistical Local Areas ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format
#
zip/sla11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_sla11aaust_shape.zip&1259.0.30.001&Data%20Cubes&56A7AA594A7F44F9CA2578CC0011CE44&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

