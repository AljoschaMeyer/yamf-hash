# YAMF-Hash

> Yet-Another-Multi-Format - Hash

Self-describing cryptographic hashes. Unlike the [multiformats](https://github.com/multiformats/multihash) one, this does not try to capture as many hash functions as possible, rather it starts out with a single one and will add new ones only when the old one gets broken.

A yamf-hash is a pair of a numeric identifier for a hash function, and a hash digest. The currently supported functions:

| Hash Function                                  | Numeric Id | Digest Length (Bytes) |
|------------------------------------------------|------------|-----------------------|
| [Blake2b](https://tools.ietf.org/html/rfc7693) | 0          | 64                    |

## Binary Encoding

The binary encoding of a yamf-hash is the binary [stlv](https://github.com/AljoschaMeyer/stlv) encoding with the numeric id from the above table as the type, and the digest as the value.

A *canonic binary yamf-hash* uses the canonic binary encoding of the stlv.
