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
| BS=1| 8GB |
| BS=2| 11GB |
| BS=4| 24GB |
| BS=8| 32GB |

Throughput (batchsize_x_updates/sec) 

|   | 2060  | 2070  | 2080  |  1080 Ti | 2080 Ti | TitanRTX | Quadro RTX 6000 | V100 | Quadro RTX 8000 |
|---|---|---|---|---|---|---|---|---|---|
| BS=1| OOM | 3.21 | 4.00 | 3.91 | 4.86 | 5.05 | 5.20 | | 5.04 |
| BS=2| OOM | OOM | OOM | 7.56 | 9.4 | 9.8 | 9.82 | | 9.60 |
| BS=4| OOM | OOM | OOM | OOM | OOM | 18.16 | 18.10 | | 16.89 |
| BS=8| OOM | OOM | OOM | OOM | OOM | OOM | OOM | 56.30 | 27.5 |
