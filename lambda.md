Installation
===

```bash
sudo pip3 install virtualenv

sudo apt-get install python3-dev

cd mt-dnn
virtualenv -p /usr/bin/python3.6 venv-mt-dnn
. venv-mt-dnn/bin/activate

pip install -r requirements.txt

```


Data
===

```bash
sh download.sh 

python prepro.py
```


Train
===

```bash
cd scripts
./run_mt_dnn.sh batch_size gpu_id
```

| Batch Size | Memory  |
|---|---|
| BS=1| 11GB |
| BS=2| 11GB |
| BS=4| 24GB |
| BS=8|  |

Throughput (batchsize_x_updates/sec) 

|   | 2060  | 2070  | 2080  |  1080 Ti | 2080 Ti | TitanRTX | Quadro RTX 6000 | V100 | Quadro RTX 8000 |
|---|---|---|---|---|---|---|---|---|---|
| BS=1| OOM | OOM | | | | | 4.86 | 5.05 | | | |
| BS=2| OOM | OOM | | | | | 9.4 | 9.8 | | | |
| BS=4| OOM | OOM | | | | | OOM | 18.16 | | | |
| BS=8| OOM | OOM | | | | | OOM | OOM | | | |