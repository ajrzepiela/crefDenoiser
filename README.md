1. To create the dataset needed for training, download the protein half-maps and mask files from EMDB FTP server
```
rsync -rlpt -v -z --port=33444 rsync.rcsb.org::emdb/structures/EMD-*/masks/*msk_1.map ./masks/
rsync -rlpt -v -z --port=33444 rsync.rcsb.org::emdb/structures/EMD-*/other/*.gz ./maps/
```
2. Run the ```tf_records_masks2023.py``` script to construct a tfRecords dataset
```
python tf_records_masks2023.py
```
3. Modify entries in ```settings.py``` according to your log and dataset locations and run ```models3.py``` to start training
```
python models3.py
```
