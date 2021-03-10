# wsj0-mix generation scripts, in Python.
## Usage
To generate wsj0-mix data, run:
```bash
python generate_wsjmix.py -p wsj0_path -o output_path -n n_sources -sr sr
```
Where: 
- `wsj0_path` is the path to the folder containing the `wsj0` folder 
  (itself containing `si_trs`, `si_et_05`, etc.).
  
- `output_path` is the output folder where `2speakers`, `3speakers` folder will be created. 
Default `./wsj0-mix`

- `n_sources` is the number of sources you'd like to simulate (from 2 to 5). Default 2.

- `sr` is the sampling frequency. Default 8000.

To generate all the possible versions of wsj0-mix, run
```bash
for nsrc in 2 3 4 5; do
  for sr in 8000 16000; do
    python generate_wsjmix.py -p wsj0_path -o output_path -n $nsrc -sr $sr
  done
done
``` 