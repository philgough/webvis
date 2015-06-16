PROCESSED_ITEMS_AUSTRALIA = \
	zip/sla11aaust_shape.zip \
	zip/ssd11aaust_shape.zip \
	zip/sd11aaust_shape.zip \
	zip/ste11aaust_shape.zip \
	zip/sdist11aaust_shape.zip \
	zip/lga11aaust_shape.zip \
	zip/srs11aaust_shape.zip \
	zip/sr11aaust_shape.zip \
	zip/msr11aaust_shape.zip	

PROCESSED_ITEMS_QLD = \
	zip/mb_2011_qld_shape.zip 

PROCESSED_ITEMS_SA = \
	zip/sa1_2011_aust_shape.zip \
	zip/sa2_2011_aust_shape.zip \
	zip/sa3_2011_aust_shape.zip \
	zip/sa4_2011_aust_shape.zip

TOPOJSON = node_modules/.bin/topojson
TOPOMERGE = node_modules/.bin/topojson-merge

all: $(PROCESSED_ITEMS_AUSTRALIA) $(PROCESSED_ITEMS_QLD) 

australia: $(PROCESSED_ITEMS_AUSTRALIA) 
qld: $(PROCESSED_ITEMS_QLD) 
sa: $(PROCESSED_ITEMS_SA)

#########################################################################################

# Data From:
# http://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1270.0.55.001July%202011?OpenDocument

#
# Statistical Area Level 1 (SA1) ASGS Ed 2011 Digital Boundaries in ESRI Shapefile Format 
#
zip/sa1_2011_aust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1270055001_sa1_2011_aust_shape.zip&1270.0.55.001&Data%20Cubes&24A18E7B88E716BDCA257801000D0AF1&0&July%202011&23.12.2010&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Area Level 2 (SA2) ASGS Ed 2011 Digital Boundaries in MapInfo Interchange Format 
#
zip/sa2_2011_aust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1270055001_sa2_2011_aust_shape.zip&1270.0.55.001&Data%20Cubes&7130A5514535C5FCCA257801000D3FBD&0&July%202011&23.12.2010&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Area Level 3 (SA3) ASGS Ed 2011 Digital Boundaries in MapInfo Interchange Format 
#
zip/sa3_2011_aust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1270055001_sa3_2011_aust_shape.zip&1270.0.55.001&Data%20Cubes&AD2BD90E5DC0F4C7CA257801000D59E3&0&July%202011&23.12.2010&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Area Level 4 (SA4) ASGS Ed 2011 Digital Boundaries in MapInfo Interchange Format 
#
zip/sa4_2011_aust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1270055001_sa4_2011_aust_shape.zip&1270.0.55.001&Data%20Cubes&B18D49356F3FDA5FCA257801000D6D2E&0&July%202011&23.12.2010&Latest" -O $@.download
	mv $@.download $@

#########################################################################################

#
# Queensland Mesh Blocks ASGS Ed 2011 Digital Boundaries in ESRI Shapefile Format 
#
zip/mb_2011_qld_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1270055001_mb_2011_qld_shape.zip&1270.0.55.001&Data%20Cubes&28231DC5E634B991CA257801000CC024&0&July%202011&23.12.2010&Latest" -O $@.download
	mv $@.download $@

#########################################################################################

#
# Statistical Local Areas ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format
#
zip/sla11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_sla11aaust_shape.zip&1259.0.30.001&Data%20Cubes&56A7AA594A7F44F9CA2578CC0011CE44&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Subdivision ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format 
#
zip/ssd11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_ssd11aaust_shape.zip&1259.0.30.001&Data%20Cubes&4913953D966B9E79CA2578CC0011E833&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Division ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format
#
zip/sd11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_sd11aaust_shape.zip&1259.0.30.001&Data%20Cubes&A2521D72ABA3D177CA2578CC0011FBFE&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# State and Territory ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format 
#
zip/ste11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_ste11aaust_shape.zip&1259.0.30.001&Data%20Cubes&D39E28B23F39F498CA2578CC00120E25&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

shp/ste11aaust_shape.shp: zip/ste11aaust_shape.zip
	mkdir -p $(dir $@)
	unzip -d shp $<
	touch $@

# topojson -q 5e2 --simplify-proportion 0.1 -o mapa2.json STE11aAust.shp australia=STE11aAust.shp
topo/ste11aaust_shape.json: shp/STE11aAust_shape.shp
	mkdir -p $(dir $@)
	mkdir -p data
	topojson -o data/australia.json shp/STE11aAust.shp australia=shp/STE11aAust.shp
#	topojson -q 5e2 --simplify-proportion 0.1 -o data/australia.json shp/STE11aAust.shp australia=shp/STE11aAust.shp
#	$(TOPOJSON) \
#		-q 5e5 \
#		--simplify-proportion 0.1 \
#		-o $@ \
#		$< \
#		australia=$<

#	$(TOPOJSON) \
#		--quantization 1e5 \
#		--id-property=+iso_n3 \
#		-- countries=shp/ne_$*_admin_0_countries.shp \
#		| $(TOPOMERGE) \
#			-o $@ \
#			--io=countries \
#			--oo=land \
#			--no-key

#
# Statistical District ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format 
#
zip/sdist11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_sdist11aaust_shape.zip&1259.0.30.001&Data%20Cubes&1A91E60D88532CEACA2578CC0012174E&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# Local Government Area ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format
#
zip/lga11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_lga11aaust_shape.zip&1259.0.30.001&Data%20Cubes&03275B7661181087CA2578CC001223EA&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Region Sector ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format 
#
zip/srs11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_srs11aaust_shape.zip&1259.0.30.001&Data%20Cubes&97AA197CD16B9D16CA2578CC00123B31&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# Statistical Region ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format
#
zip/sr11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_sr11aaust_shape.zip&1259.0.30.001&Data%20Cubes&B8003880BC09FA5BCA2578CC00124E25&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

#
# Major Statistical Region ASGC Ed 2011 Digital Boundaries in ESRI Shapefile Format
#
zip/msr11aaust_shape.zip:
	mkdir -p $(dir $@)
	wget "http://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&1259030001_msr11aaust_shape.zip&1259.0.30.001&Data%20Cubes&F087093CCDF2C68DCA2578CC0012607E&0&July%202011&14.07.2011&Latest" -O $@.download
	mv $@.download $@

