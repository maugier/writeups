# CTF Writeup: TinyCTF 2014: Crypto 200

## Analyse

Pour ce problème, on nous donne les deux fichiers suivants:

    BJQOmVgJuDRqciWk748XXvMDHTP5dbU5jK4R4KzLkZXE41EnS7nbrB0bmBmuZ56NMARX8+X48xFQ
    ZI+Dk8v1A+QLERQLiopR0ivFvHT9v9oOjavMZwTRKKop/kgFOIAb1N5CLm8aIh5HH3XYVaSQMyie
    H1jg216NKi2rRzkSsbNe0FUokMi3MkYmbCftuQsVCaLV0gkjbiMFDEWs+BLfmLG+OovN/5iRx3Pa
    oXty2z/VnNK2XuED7Hsk4TWOvhTMuGgxphffEGdN2EKTnd1FXnQdT8jxQhkXt4LRZgZRpTlpKKlG
    Ybzfnw0vlW/GyiOEeO9EcB7vs7DlYQ3VVi/OZr4RsbXZ/8pjalIDfXzmzUTqgQuoTEnAKuKb0t4/
    +gOujwWz5jPw8RxRNSjxQExmIXudVgXm8IacJb8CS5PONa7yqxbQ8U80yFDsHRPHPka9WGhpA79j
    dAFCV5CV19KT+L01q/ZTcp7NDoSVSnOgfYUEygPTqkSmsI13bs+JScW3HVLiAA69ZhCj4Y9/c55J
    WOBw7JuclJPJkNY3hQ0qrXUvtghZ9nanb8Hz4pVqvt0r2460n4isC5rgHTyEgYdTaAPHqZ5h6eTZ
    4QrWCVLpOHtCQsJNBvP9skf0yLhUJbSajbanFhRKDmInPLcicJ+W+cJU6unV/JsaCrrjCvnaSa92
    VXKQglHpm+rxYFpABDt86M+91JzbwzwCFtlmFlpfBFmds9zCQEE5JJvmyueLV5QpNFGmkCwYt3GX
    WUdbMbl25AyNV5+EICgIg29d3wTUoe3yJVXHYS3xlz5Fs0MEXQK1qQp2DOu2nvhi/+LAI+4+5fOW
    jAcSDpuNA2/ezK7Z8bfOZ49Ew+UHv1AVdRB4+ZDv4kj+94fzRXATRnkgfVmcqy1YUkJlFn068iCD
    JaZx+aDO2UuQISHqpu6YLUwjtUP4Y1gCkaqxNP6oLJpxHRLSvBnvoWjAW+BwJYRCxG2pWrbx2/W+
    +EX6SFJOvNox1eGcy2mDW9UIEu8BF/8z9DGQcvlDWctp65URM6+y1y4nc6VIDQSWk4kVPYMb5gB5
    FcVx+IF9bVbtbtXf2l2FXk3asy7P2rwrXSI1cS0TImCTvaxsfCg0Fc3eVZtjjUKhnKl6hCwBv4i9
    w+xV9x3M5bDa0lJwBGAa4rScXBoT7Pt+cXCTg4K3dyTCCK7Y18sfsjooWWweQ7ZNRjNsENrhgUb6
    9NXrjELBZ0EJA9dvgP3eR5vv+1age7nO96VZV5tjfWJbeD50xJXElbFiqYNAwRzNw/1qEn8WN1f5
    TL/8RUK5E+mTJY/9+F97BL5jcSbcGVp6aRDZQsyHAhShmKXphKRKksCCd4ZRUoC/c3m+ve/lecfl
    qaaRFvYDkR0BAQ0cqTiCyP5Hkb9YCmBzFETrCfH1D8oN37nZkxCp7WmVUesXwWQz

et 

    -----BEGIN PUBLIC KEY-----
    MIIEUzANBgkqhkiG9w0BAQEFAAOCBEAAMIIEOwKCBDIGLT1hySRSYwFH6JZw////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    ////////////////////////////////////////////////////////////////
    //8CAwEAAQ==
    -----END PUBLIC KEY-----

On remarque immédiatement la structure étrange de la clef. Affichons là avec openssl:

    openssl rsa -pubin -noout -text <crypto200.pub
    Public-Key: (8587 bit)
    Modulus:
        06:2d:3d:61:c9:24:52:63:01:47:e8:96:70:ff:ff:
        ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:
        ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:
    ...
        ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:
        ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:
        ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:ff:
        ff:ff:ff:ff:ff:ff:ff:ff:ff
    Exponent: 65537 (0x10001)
    

La clef est très grande, mais remplie de bits 1. Le deuxième fichier, une fois décodé, fait 1074 bytes, soit 8592 bits; tout juste assez pour contenir un nombrebrut de la même taille de la clef.

## Casser la clef

La clef publique exhibe une forme particulière. Pouvons nous l'exploiter ?

La clef fait 8587 bits, le préfixe du module (`06:2d:3d:61:c9:24:52:63:01:47:e8:96:70`) fait exactement 
