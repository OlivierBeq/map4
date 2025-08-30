:warning: This version of MAP4 removes any dependence on tmap and replaces it with MHFPEncoder from mhfp.
Thus, this version can be used with Windows.

# MAP fingerprint - Design and Documentation  

The canonical, not isomeric, and rooted SMILES of the circular substructures `CS` from radius one up to a user-given radius `n` (default `n=2`, `MAP4`) are generated for each atom. All atom pairs are extracted, and their minimum topological distance `TP` is calculated. For each atom pair `jk`, for each considered radius `r`, a `Shingle` is encoded as: `CS`<sub>`rj`</sub>`|TP`<sub>`jk`</sub>`|CS`<sub>`rk`</sub> , where the two `CS` are annotated in alphabetical order, resulting in n Shingles for each atom pairs. 

![MAP4 atom pair encoding scheme](https://github.com/OlivierBeq/map4/raw/master/graphics/shingles.png)

The resulting list of Shingles is hashed using the unique mapping `SHA-1` to a set of integers `S`<sub>`i`</sub>, and its correspondent transposed vector `s`<sup>`T`</sup><sub>`i`</sub> is MinHashed.

![MihHash](https://github.com/OlivierBeq/map4/raw/master/graphics/minhash.png)

To install map4 trough pip:
```
pip install map4-ojmb
```

Run the fingerprint from terminal
```
cd map4
python map4.py -i smilesfile.smi -o outputfile
```

Or import the MAP4Calculator class in your python file (see `test.py`)
