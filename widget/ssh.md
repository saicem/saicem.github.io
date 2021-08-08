# ssh

## ssh-keygen

```man
-b bits
    Specifies the number of bits in the key to create.  For RSA keys, the minimum size is 1024 bits and the
    default is 3072 bits.  Generally, 3072 bits is considered sufficient.  DSA keys must be exactly 1024
    bits as specified by FIPS 186-2.  For ECDSA keys, the -b flag determines the key length by selecting
    from one of three elliptic curve sizes: 256, 384 or 521 bits.  Attempting to use bit lengths other than
    these three values for ECDSA keys will fail.  ECDSA-SK, Ed25519 and Ed25519-SK keys have a fixed length
    and the -b flag will be ignored.

-C comment
    Provides a new comment.

-f filename
    Specifies the filename of the key file.

-t dsa | ecdsa | ecdsa-sk | ed25519 | ed25519-sk | rsa
    Specifies the type of key to create.  The possible values are “dsa”, “ecdsa”, “ecdsa-sk”, “ed25519”,
    “ed25519-sk”, or “rsa”.

    This flag may also be used to specify the desired signature type when signing certificates using an RSA
    CA key.  The available RSA signature variants are “ssh-rsa” (SHA1 signatures, not recommended),
    “rsa-sha2-256”, and “rsa-sha2-512” (the default).
```

## 使用ssh连接服务器

ssh连接 将 rsa_id.pub 写入 authorized_keys

### 权限要求

- `chmod 700 -R .ssh`
- `chmod 600 authorized_keys`
