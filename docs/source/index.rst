Brotlipy: Python Bindings to the Brotli Compression Algorithm
=============================================================

Brotlipy is a collection of `CFFI-based`_ bindings to the `Brotli`_ compression
reference implementation as written by Google. This enables Python software to
easily and quickly work with the Brotli compression algorithm, regardless of
what interpreter is being used.

Brotlipy has a very similar interface to the standard library's ``zlib``
module:

.. code-block:: python

    import brotli

    # Decompress a Brotli-compressed payload in one go.
    decompressed_data = brotli.decompress(compressed_data)

    # Alternatively, you can do incremental decompression.
    d = brotli.Decompressor()
    for chunk in chunks_of_compressed_data:
        some_uncompressed_data = d.decompress(chunk)

    remaining_data = d.flush()

    # You can compress data too.
    compressed = brotli.compress(uncompressed_data)

For more details on the API, see :doc:`api`.

.. _CFFI-based: https://cffi.readthedocs.org/en/latest/
.. _Brotli: https://github.com/google/brotli


Documentation
-------------

.. toctree::
   :maxdepth: 2

   installation
   api


License
-------

Brotlipy's source code is made available under the MIT license. Brotli itself
is licensed under Version 2.0 of the Apache Software License.
