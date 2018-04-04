# Functional Map of the World (fMoW) Dataset

There are two versions of the dataset: **fMoW-full** and **fMoW-rgb**. fMoW-full is in TIFF format, contains 4-band and 8-band multispectral imagery, and is quite large at ~3.5TB in size. fMoW-rgb is in JPEG format, all multispectral imagery has been converted to RGB, and it is significantly smaller in size at ~200GB.

Please see the [fMoW flyer](https://github.com/fMoW/dataset/raw/master/IARPA-fMoW.pdf) for more info about the challenge.
**Note that the fMoW challenge has now ended.**

## References

If you use our dataset or code, please cite [our paper](https://arxiv.org/abs/1711.07846):

```
@inproceedings{fmow2018,
  title={Functional Map of the World},
  author={Christie, Gordon and Fendley, Neil and Wilson, James and Mukherjee, Ryan},
  booktitle={CVPR},
  year={2018}
}
```

## Categories

```
["airport", "airport_hangar", "airport_terminal", "amusement_park", "aquaculture", "archaeological_site", "barn", "border_checkpoint", "burial_site", "car_dealership", "construction_site", "crop_field", "dam", "debris_or_rubble", "educational_institution", "electric_substation", "factory_or_powerplant", "fire_station", "flooded_road", "fountain", "gas_station", "golf_course", "ground_transportation_station", "helipad", "hospital", "impoverished_settlement", "interchange", "lake_or_pond", "lighthouse", "military_facility", "multi-unit_residential", "nuclear_powerplant", "office_building", "oil_or_gas_facility", "park", "parking_lot_or_garage", "place_of_worship", "police_station", "port", "prison", "race_track", "railway_bridge", "recreational_facility", "road_bridge", "runway", "shipyard", "shopping_mall", "single-unit_residential", "smokestack", "solar_farm", "space_facility", "stadium", "storage_tank", "surface_mine", "swimming_pool", "toll_booth", "tower", "tunnel_opening", "waste_disposal", "water_treatment_facility", "wind_farm", "zoo"]
```

## Download

There are two official ways to download the dataset: from AWS or using BitTorrent.

### AWS

The fMoW datasets are available on AWS in [Requester Pays](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html) buckets at:

  * **fMoW-full**: s3://fmow-full
  * **fMoW-rgb**: s3://fmow-rgb

Or without requester pays at:

  * **fMoW-full**: s3://spacenet-dataset/fmow/fmow-full
  * **fMoW-rgb**: s3://spacenet-dataset/fmow/fmow-rgb
 
Accessing the data through AWS is possible using tools such as the [AWS CLI](https://aws.amazon.com/documentation/cli/). For example, to get a directory listing using the AWS CLI run the following commands:
```
aws s3 ls s3://fmow-full --request-payer requester
aws s3 ls s3://fmow-rgb --request-payer requester
```
or without requester pays:
```
aws s3 ls s3://spacenet-dataset/fmow/fmow-full/
aws s3 ls s3://spacenet-dataset/fmow/fmow-rgb/
```

To download the manifest.json.bz2 files that list all images and metadata present in each bucket, run the following commands:
```
aws s3api get-object --bucket fmow-full --key manifest.json.bz2 --request-payer requester
aws s3api get-object --bucket fmow-rgb --key manifest.json.bz2 --request-payer requester
```
or without requester pays:
```
aws s3 cp s3://spacenet-dataset/fmow/fmow-full/manifest.json.bz2 ./
aws s3 cp s3://spacenet-dataset/fmow/fmow-rgb/manifest.json.bz2 ./
```

### BitTorrent

Using the client of your choice, you can add the following torrent files to download the corresponding subsets of the fMoW dataset:

  * [fMoW-full train and val](https://github.com/fMoW/dataset/raw/master/fMoW-full_trainval_v1.0.0.torrent)
  * [fMoW-full test](https://github.com/fMoW/dataset/raw/master/fMoW-full_test_v1.0.0.torrent)
  * [fMoW-full val sample with false detections](https://github.com/fMoW/dataset/raw/master/fMoW-full_val_sample_v1.1.0.torrent)
  * [fMoW-full sequestered and ground truth data](https://github.com/fMoW/dataset/raw/master/fMoW-full_seqandgt_v1.2.1.torrent)
  * [fMoW-rgb train and val](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_trainval_v1.0.0.torrent)
  * [fMoW-rgb test](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_test_v1.0.0.torrent)
  * [fMoW-rgb val sample with false detections](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_val_sample_v1.1.0.torrent)
  * [fMoW-rgb sequestered and ground truth data](https://github.com/fMoW/dataset/raw/master/fMoW-rgb_seqandgt_v1.2.1.torrent)

## Additional details

The train and val sets were released to competitors with category labels and a rich set of metadata fields. The test and seq sets had category labels removed and a small amount of noise added to many metadata fields. Certain fields, such as GPS coordinates, were removed from all sets during the challenge. However, now that the challenge has ended, the sequestered and ground truth data has been released, which contains all raw metadata, including category labels and GPS coordinates, for every image. 

Joining these ground truth metadata files with the original test and seq imagery does require a small amount of effort. In each of the ground truth archives for fMoW-full and fMoW-rgb there is a mapping JSON file. This mapping file provides the association between each test and seq image and its corresponding metadata. You can also use this mapping file to reorganize the test and seq data into category and temporal sequence folders similar to the train and val sets.
  
## License

This data is licensed under the [Functional Map of the World Challenge Public License](https://github.com/fMoW/dataset/raw/master/LICENSE). This new license is similar to the previous license with modifications to clarify that algorithms trained on challenge data are not considered adapted material.