# Functional Map of the World (fMoW) Dataset

There are two versions of the dataset: **fMoW-full** and **fMoW-rgb**. fMoW-full is in TIFF format, contains 4-band and 8-band multispectral imagery, and is quite large at ~3.5TB in size. fMoW-rgb is in JPEG format, all multispectral imagery has been converted to RGB, and it is significantly smaller in size at ~200GB.

Please see the [fMoW flyer](https://github.com/fMoW/dataset/raw/master/IARPA-fMoW.pdf) for more info about the challenge.

## Categories

```
["airport", "airport_hangar", "airport_terminal", "amusement_park", "aquaculture", "archaeological_site", "barn", "border_checkpoint", "burial_site", "car_dealership", "construction_site", "crop_field", "dam", "debris_or_rubble", "educational_institution", "electric_substation", "factory_or_powerplant", "fire_station", "flooded_road", "fountain", "gas_station", "golf_course", "ground_transportation_station", "helipad", "hospital", "impoverished_settlement", "interchange", "lake_or_pond", "lighthouse", "military_facility", "multi-unit_residential", "nuclear_powerplant", "office_building", "oil_or_gas_facility", "park", "parking_lot_or_garage", "place_of_worship", "police_station", "port", "prison", "race_track", "railway_bridge", "recreational_facility", "road_bridge", "runway", "shipyard", "shopping_mall", "single-unit_residential", "smokestack", "solar_farm", "space_facility", "stadium", "storage_tank", "surface_mine", "swimming_pool", "toll_booth", "tower", "tunnel_opening", "waste_disposal", "water_treatment_facility", "wind_farm", "zoo"]
```

## Download

There are currently two official ways to download the dataset: from AWS or using BitTorrent.

### AWS

The fMoW datasets are available on AWS in [Requester Pays](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html) buckets.

  * **fMoW-full**: s3://fmow-full
  * **fMoW-rgb**: s3://fmow-rgb

Accessing the data through AWS is possible using tools such as the [AWS CLI](https://aws.amazon.com/documentation/cli/). For example, to get a directory listing using the AWS CLI run the following commands:
```
aws s3 ls s3://fmow-rgb --request-payer requester
aws s3 ls s3://fmow-full --request-payer requester
```
To download the manifest.json.bz2 files that list all images and metadata present in each bucket run the following commands:
```
aws s3api get-object --bucket fmow-rgb --key manifest.json.bz2 --request-payer requester
aws s3api get-object --bucket fmow-full --key manifest.json.bz2 --request-payer requester
```

### BitTorrent

Using the client of your choice, you can add the following torrent files to download the corresponding subsets of the fMoW dataset:

  * [fMoW-full train and val](https://github.com/fMoW/dataset/raw/master/fMoW-full_trainval_v1.0.0.torrent)
  * [fMoW-full test](https://github.com/fMoW/dataset/raw/master/fMoW-full_test_v1.0.0.torrent)
  * [fMoW-full val sample with false detections](https://github.com/fMoW/dataset/raw/master/fMoW-full_val_sample_v1.1.0.torrent)
  * [fMoW-rgb train and val](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_trainval_v1.0.0.torrent)
  * [fMoW-rgb test](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_test_v1.0.0.torrent)
  * [fMoW-rgb val sample with false detections](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_val_sample_v1.1.0.torrent)
  
## License

This data is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).