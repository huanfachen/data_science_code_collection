# Parallel computing in Python using mapply

Author: [Huanfa Chen](github.com/huanfachen)

Last update: 28/06/2022

1. What is mapply?

   mapply is a Python package for multiprocessing computing. It will patch Pandas, adding multi-core methods to PandasObject.

   Comparison: there are several packages for multiprocessing computing in Python. Where [`pandarallel`](https://github.com/nalepae/pandarallel) only requires [`dill`](https://github.com/uqfoundation/dill) (and therefore has to rely on in-house multiprocessing and progressbars), [`swifter`](https://github.com/jmcarpenter2/swifter) relies on the heavy [`dask`](https://github.com/dask/dask) framework, converting to Dask DataFrames and back. In an attempt to find the golden mean, `mapply` is highly customizable and remains lightweight, leveraging the powerful [`pathos`](https://github.com/uqfoundation/pathos) framework, which shadows Python's built-in multiprocessing module using `dill` for universal pickling.

2. How many CPUs will be used by mapply?

   - In the **init** function, the user can set the number of processes. **n_workers** ([*int*](https://docs.python.org/3/library/functions.html#int)) – Maximum amount of workers (processes) to spawn. Might be lowered depending on chunk_size and max_chunks_per_worker. Will throw a warning if set higher than is sensible (see [`mapply.parallel.sensible_cpu_count()`](https://mapply.readthedocs.io/en/stable/_code_reference/mapply.html#mapply.parallel.sensible_cpu_count)).
   - Details of the init function are [here](https://mapply.readthedocs.io/en/stable/_code_reference/mapply.html).
   - 

3. References

   - [mapply documentation](https://mapply.readthedocs.io/en/stable/_code_reference/mapply.html)
   - 