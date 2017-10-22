# Ugly Duckling

## Given Problem

The problem is given as follows:

    $ cat input.txt
    
    Pour réussir ce challenge tu dois envoyer la signature valide du message "Please give me the flag" en utilisant le même format de signature que ci-dessous :
    
    -----BEGIN PUBLIC KEY-----
    MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEpuXtxRVM66Bs0wooq288G3VXUHlr
    bFTkMdbFM+SVYaFySfyUggFwTNKiDuTayOpLQNF6ypapU3eXBnIkWdcqSw==
    -----END PUBLIC KEY-----
    
    Texte   ECDSA signature (der format)
    'A digital signature is an elec'        MEUCIDNzKttS2wQHNwzVXyImvgtfsfo3RunkXx51nzkJky4hAiEAqxs7FnifkxpkmgT/TKuArbkQfxDrpNrWgRhjw2v9XYY=
    'tronic analogue of a written s'        MEUCIC+ZtRvik6shfweDx7pltMU7+hWz/DZIlbuj3JBTE//qAiEA2vbJh18ywznfxsr4s1EBqI6F3nvH226WmwR8TfVsMEQ=
    'ignature; the digital signatur'        MEUCIQDYOVf/wraAaEU2O81ECbnROj9H0KuRbf0fl/LocEKPFQIgbu4fV5T80A3tnYSi+eCYR89q7C2iZKKlImf/SywrMxg=
    'e can be used to provide assur'        MEYCIQDQF2s2MvGiYzFGke39SCTEjC8Q95pq8PzLw1ZuqxWSzAIhAJzRcgwZFV7etGoMS6GyVmuSAhSX5c0kkJDT2fbZdHqZ
    'ance that the claimed signator'        MEQCIGwB5PAkCYjy4sySscUbP2O24xQ0eXTOzhEnCU5d7v4rAiAfqBgrGVL5jWC49rY051aF2EH2pEP5TUFCx305hgXDkw==
    'y signed the information. In a'        MEUCIArXFq3NLflM1aG5BJU9V7UTt464jLjZ4DXkPpccBW73AiEAs/tjla3KvobfedoELIXyrrppG+G0sAaIvLYMnBQq6vc=
    'ddition, a digital signature m'        MEYCIQC6zHS5/+pfZlN2jzWVZBW6VNlA43exr61hQlL1BACVggIhAJt2ar7DZDJ/vXAy5WdRqWetyLAWUWWbT7bTN4bm+GK3
    'ay be used to detect whether o'        MEUCIQC8dTE25xekSpbyjLBWcrl440BJxEmrStIU7noKyj8ecAIgNFyjIz0AWNIZ+ZbRukOXm/Z07UuMBUohddqmHqbFBiw=
    'r not the information was modi'        MEQCIEw5Ar8j7/msmmDr1kqqUwzvIs/Vnga/kD3OLE9sK3cYAiBGfT0gehy5aA9mE5FyBethtFykxLm3A1H2KeKWkseZLQ==
    'fied after it was signed (i.e.'        MEUCIFjR6vlS/D+nFcZtBXBgRN1XQHHMX3CZ5FSbfVi3a5EDAiEAk386UuIa+NfFHVkdc0UqrsNshf5qvJtw70Yf1RaolPg=
    ', to detect the integrity of t'        MEUCIQCmGscR5TXMmdEd5pAa/mXL4ScZlg0eWx56P9dBG2V7PwIgDkazr6fwr6YBDbABw6xMvPy2sGmp/wHNyZvUdMBw/b8=
    'he signed data). These assuran'        MEQCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiArE3Hy+NPD3AYEuZTQy7vjzHVSLK0YsbEoPLZRZnI3fA==
    'ces may be obtained whether th'        MEQCICLL5y+sABYiJPW0TunEwvvHo0er7kFYgknxlqA1HoEjAiA5KohKdl1cxUg3GPa/aoiRqXoOHSF/4NdXxffYV4mPdg==
    'e data was received in a trans'        MEUCICRfjlf/nIOMEbSzeVL/5hy3M/dC/jqKjHf3AiWYD1MWAiEA1J8A6YnQMimn6ZyE7b92DdFBSmwUC7+qomPHYx8kwkc=
    'mission or retrieved from stor'        MEQCIG5Kuc7MbAlWczmSQpp/N8SljidJXRZexQ5iko6VVDL6AiAM07//x/OPcoLzcwEu7VtD/l37DAbapNyJ/WbRvrAdHg==
    'age. A properly implemented di'        MEUCIFbd+3sIcEKkWdg+fkaCz1+bzXVjHTcer02nnf2a5XZdAiEA00gEkt6V7NVmqXMTrPXDDKzBKmAnXvAxF/RnRh/Tpv4=
    'gital signature algorithm that'        MEYCIQDK4vyVFYNrPCpA5ET/uU5qD31h11Xu4dSt82zNg/reqwIhAMud2+okRJjkmbocXLw/oBOSRnFjokBRV3V5hnSmO0T1
    ' meets the requirements of thi'        MEQCIDDUeIXikKGfrGgiUvPqqpEizbNmaedtWlyXIvZwj/D4AiAG9dubFytj5Njqxf9zh/ZKVmQCtIoj0LGp3W1VvpMa/w==
    's Standard can provide these s'        MEQCIE7UTRM8TVjQHMS0KsCEMHVii8Ulaw/Bf8SV2668QPeAAiAHZAzWYpE7BcqJ1gNN8hCv1gX4ybiGDDvpPg6C1JnP2A==
    'ervices. A digital signature a'        MEUCIHWoQIQYAy3gc2VOQCsmyGKW1X5pPt79ORThS2I9d/pJAiEA0HkvYzawmZoR9b6ZoxCocuv9sD+8lrzQ8O9hGSB3P9E=
    'lgorithm includes a signature '        MEUCIDsBNIHvhQ5+T+ndF/hQfZFMPaen107691pH8W9mun29AiEAjmjEqHKGdx2pb8wyvMC9dnKWsP/7YLdd2k1z+s6BkKs=
    'generation process and a signa'        MEQCIAEff3DMImrnEEppqNz9qfup7Av24NKYhLsyeq+ApmObAiB7yC4dmPsZW16I+h6wQMG87Q2dajDzjsZD/kwMEGuH6A==
    'ture verification process. A s'        MEUCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiEAkhWDrap8G1x5mMSXJtdeJ56hx61G7sg4ojS+i4eabF4=
    'ignatory uses the generation p'        MEUCIQDfhyzEKt8Qurm4LK4FtuRnPTp1KNyf6fXyYUNDRHXbOwIgMEog89tFr1fWWxx8P2unXoUBDu/SAJiE/40T1Gl2KlM=
    'rocess to generate a digital s'        MEYCIQCQ9GixXBtt+joG5D3c1ZVoj2aCIGjxw22OGHZNR/GpYgIhAJwWR2Nkr0Ms+hQF/dcWg2fNBqZmBI9m4Br/WmwATlPV
    'ignature on data; a verifier u'        MEQCICCETeP/NzX32baDeo+mbFq0YCPSlaEJZDiur5gZ15ZuAiBqgCmVSjtXK2NL5SoVmIdXUZvNrbU6gnKW9gaF59vpoQ==
    'ses the verification process t'        MEQCIAWqoBkB5OZmos3tVkNkLyd30cHOB//Buo9WkkDme5+jAiBtnnaac51pCOtAWJLbrfYoJJya0FSiNVy8dcctZ5242A==
    'o verify the authenticity of t'        MEYCIQCuLA1pnnD8F96Ru1A+MJKEzNpEKeHpLo84FBysXvREhgIhAJcvUWlXDioZG06CeisZWoC/nhFISm84Q4gaSPYnCiLt
    'he signature. Each signatory '         MEYCIQD4uTDW+H3EGJLdrONv96Si1xwFuGpGbJXJRbCEq9Q9XQIhAKaMvng/m7yEt4BVTWiUHijBkKD8QFlgRqe7s37PKWWn
    'has a public and private key a'        MEUCIQDB74Y+I95JejE5sscxrF3/pczW9DuqYkOXUT7cHY7SLQIgBgoM2cELtLMxQZ2UPOT6hO4hD3PMbA5WesI4i+AtgLI=
    'nd is the owner of that key pa'        MEYCIQCT9iPHDQFb+O7koDuizf/FY9XrNK96VIdOdbcAwdIERAIhAOADAcyFiarRaxDNPu/HuZZvC+/7Trz/iiaEsNWWPM3w
    'ir. As shown in Figure 1, the '        MEYCIQCw+GJl5FfDbU0nec8CL70LVegRA70xXWJCaQVhdtCjLgIhALbEdgRtmMWCm2rZAxAhf4CqAZF71Zzmq2W0yXPnb17X
    'private key is used in the sig'        MEYCIQDkCroMVPLLkjrqfL3jiJxN3rGeJNZYnbUMgTJFb7L/VAIhAJXWWkZO5BS5c7Xga/BVXtrQ2HLaHB8UEQlOzj2T2lIN
    'nature generation process. The'        MEUCIFw9n2BPBX+/xhliTEmTNxGekMEAnjhUCcfPatkQr7V7AiEAh1Bvdkf2DYO58gKOAevXX5Y4GJxNXtD8UF8p6gS5QuI=
    ' key pair owner is the only en'        MEYCIQCPuwz1Q+JM6x6WrlpaDzjutYmJ0vo7g/F2+y+T1awaAwIhAPrkjswme2TYOWU3umS39m/y3oT3uaKilEi9tnUeIsWG
    'tity that is authorized to use'        MEUCIBxken6kPgmDpzrcZHa6vUSRfJNjikkJQ9rDiMRS9Mr4AiEAszoYsEzIXHawTKcKoT1XlCbro+sujqI9OUrOLMWxjkY=
    ' the private key to generate d'        MEUCIQCZ1AFzdZIdb9lfg+ptueWTR42/atSB0+r0szxT9whUOwIgWEgroIoIoMJqo5LRZZYqZIFnQERTILBrQ8XrWlD/Veg=
    'igital signatures. In order to'        MEYCIQCcXN3ks4DC/TLmBT9votOfWJ4/8jUKunhRb3w5VU1XSwIhANY8bOOCKbHA7O8K/NjFpjmK13IYLkUbHC2aCQcatBvf
    ' prevent other entities from c'        MEYCIQCYrwIA5TvvIEdQptVGhkeSnqZ38ARgU1oxMbyZZ3D5eAIhAJpzeQLj1eUr6Nhc1NGoxQFOmgGe7TpYiR/ALCAhuO8T
    'laiming to be the key pair own'        MEUCIH3pfl2Sy9GP8jpiAD2IcgJ95vQC6vJ/Sty+PnTMBwTHAiEAp0+HoILnxuEEGBFLoEXsaZWSWCKCZKmxK/Upod2rsKc=
    'er and using the private key t'        MEYCIQDluqTTkQnKwSqjJUOU4ZD2jvpyCoR/9toHWS0x5GML4gIhAOtpIx7LLgDwpAjLqh3BIJYuyh9uqHMvFRxju5kNJQ1R
    'o generate fraudulent signatur'        MEUCIBzgpFtPo1uoUbqry+z9hOJCmd6TZmJzhtxkUA613F9OAiEAiqY/clKDxaV58YbCpiQHH68OLkFwPwhpivJIgSj+qg8=
    'es, the private key must remai'        MEUCIQCjvjNiTVCbUCchpfJICBswkahOfWVnHy6yGnW6QeHurQIgM1Hd7FrFKSHCabCuY/8KH/c92q4vbqQG3HzjX45UX3U=
    'n secret. The approved digital'        MEUCIQC3rNA018ZwHwLEU4y2y9HVk3UXMEPd3QejYFxk/9aoJAIgZN6M5YsspS1nsgMkFO+lCwQdlbKBTfD5H6HvS+d7j8U=
    ' signature algorithms are desi'        MEQCIDcmhg84twVDSsEHjeBGMwO79QtnK4r9fEM8UJuGYpzQAiAvdVhfIVBD3ywk3nPxNr/ch5eCCI5rU5cByjQOGyw70g==
    'gned to prevent an adversary w'        MEUCIBhZ9OhNnarubB1yj+GZJMryhgT9i6zotYw4zjOeb7npAiEA2q647rZuES2DIfrQVIu104k87PJUFyEs/cSYAEYE2cc=
    'ho does not know the signatory'        MEUCIGZDqeSi6Z7EYTZbqaeMpUkLOkOrIL9xH9hJAmHjyHiiAiEAnvXdmluEY1tFjsNobGmIaao7NvYf2CtelrsSC3xRnR4=

For non french speakers, this means we need to forge a signature for the string "Please give me the flag", using the same format as the bunch of
valid signatures below.


## Introduction to ECC and ECDSA

ECC (Elliptic Curve Cryptography) works by manipulating points on a curve. These points are canonically defined by their coordinates `(x,y)`.
Traditionally we understand the curve as the 2D plane over the real numbers, but real numbers
are not suitable for cryptography. Thankfully, ECC works on various kind of number fields; for cryptography,
instead of the real numbers, we may chose to work in the field of integers modulo `p`, where `p` is a prime number.

The points `(x,y)` on the curve form a group, meaning we can "add" points together, and also multiply a point by an integer
(which means repeatedly adding the point with itself). The definition of point addition is a bit weird, and involves
geometry on the curve. For now, let's just assume that we know a way to perform these two operations on points of the curve.

The security of the scheme lies on the difficulty of computing the logarithm of a point. I.e., given a point `P`, and a large integer
`k`, we can easily compute the point `Q = k⋅P`. But given `Q` and `P`, there is no fast way to find `k`. (If k is small, we can use, for instance,
Daniel Shanks's baby-step giant-step algorithm)

You can check Wikipedia for the definition of the the Elliptic Curve Digital Signature Algorithm, ECDSA[1]. The public parameters are: the curve definition
(that we need to perform addition and multiplication of points), and a base curve point `G` that generates a subgroup of order `n`. Fortunately,
when using standard curves, a good generator point has been precomputed for us, along with its order `n`, which should be large.

Alice, the signer, then picks a private key, which is an integer `d`. Her public key becomes the curve point `Q = d⋅P`.


## Public key extraction

We can extract the data of the public key like this:

    $ openssl ec -pubin -noout -text < input.txt
    read EC key
    Private-Key: (256 bit)
    pub: 
        04:a6:e5:ed:c5:15:4c:eb:a0:6c:d3:0a:28:ab:6f:
        3c:1b:75:57:50:79:6b:6c:54:e4:31:d6:c5:33:e4:
        95:61:a1:72:49:fc:94:82:01:70:4c:d2:a2:0e:e4:
        da:c8:ea:4b:40:d1:7a:ca:96:a9:53:77:97:06:72:
        24:59:d7:2a:4b
    ASN1 OID: prime256v1
    NIST CURVE: P-256

This indicates the standard NIST curve (P-256) is being used. Thankfully, there is an existing Haskell package, eccrypto, that implements
operations on this curve.

Understanding the format of the public key took a little bit of googling. RFC 5480[2] states that the public key (a point on a curve) is
stored with a first byte, indicating uncompressed (0x04) or compressed (0x02 or 0x03) representation. For the uncompressed representation,
that we have here, we simply have the x-coordinate followed by the y-coordinate. The P-256 curve is defined over the field of integers
modulo a 256-bit prime, so each coordinate is 256 bits (64 bytes) long. 

The rfc does not specify the endianness of these points, but like most these formats, i will assume network endinanness here. So our public point
is:

    pub_x = 0xa6e5edc5154ceba06cd30a28ab6f3c1b755750796b6c54e431d6c533e49561a1
    pub_y = 0x7249fc948201704cd2a20ee4dac8ea4b40d17aca96a953779706722459d72a4b

## Signatures extraction

Each line is obviously base64. Could it be a standard signature format in PEM representation ? let's ask openssl, using
the first signature as a sample:

    openssl asn1parse <<< MEUCIDNzKttS2wQHNwzVXyImvgtfsfo3RunkXx51nzkJky4hAiEAqxs7FnifkxpkmgT/TKuArbkQfxDrpNrWgRhjw2v9XYY=
        0:d=0  hl=2 l=  69 cons: SEQUENCE          
        2:d=1  hl=2 l=  32 prim: INTEGER           :33732ADB52DB0407370CD55F2226BE0B5FB1FA3746E9E45F1E759F3909932E21
       36:d=1  hl=2 l=  33 prim: INTEGER           :AB1B3B16789F931A649A04FF4CAB80ADB9107F10EBA4DAD6811863C36BFD5D86

Two 256-bit integers. Wikipedia told us that an ECDSA signature is made of two integers, `r` and `s`, in the group
of integers modulo `k`, the order of the elliptic curve subgroup.

Wikipedia also tells us that a common failure for ECDSA is insufficient randomness in the selection of the nonce `k`. If a collision occurs (the same `k`
is used to sign two different messages), then it is obvious from the signatures (they will have the same `r`, but not the same `s`, and knowledge of
this information can allow us to retrieve the `k`, then in turn retrieve the private key `d`.

With only shell scripting, it is easy enough to test this possibility:

    $ for sig in $(cut -f2 signatures.txt); do openssl asn1parse <<< $sig; done |grep INTEGER |sort |uniq -c |egrep '^\s*2'
    2     2:d=1  hl=2 l=  32 prim: INTEGER           :3CDD8BCF5B734DA67714F14A8EED03C766AF75E5D0FAF1BA04B2ECA3BDDCD47A

Bingo: one of the values is repeated twice. Let's find the culprits:

    $ for sig in $(cut -f2 signatures.txt); do echo $sig; openssl asn1parse <<< $sig; done |grep -B2 3CDD8BCF5B734DA6
    MEQCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiArE3Hy+NPD3AYEuZTQy7vjzHVSLK0YsbEoPLZRZnI3fA==
        0:d=0  hl=2 l=  68 cons: SEQUENCE          
        2:d=1  hl=2 l=  32 prim: INTEGER           :3CDD8BCF5B734DA67714F14A8EED03C766AF75E5D0FAF1BA04B2ECA3BDDCD47A
    --
    MEUCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiEAkhWDrap8G1x5mMSXJtdeJ56hx61G7sg4ojS+i4eabF4=
        0:d=0  hl=2 l=  69 cons: SEQUENCE          
        2:d=1  hl=2 l=  32 prim: INTEGER           :3CDD8BCF5B734DA67714F14A8EED03C766AF75E5D0FAF1BA04B2ECA3BDDCD47A

So the signatures for these two messages are colliding:

    'he signed data). These assuran'        MEQCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiArE3Hy+NPD3AYEuZTQy7vjzHVSLK0YsbEoPLZRZnI3fA==
    'ture verification process. A s'        MEUCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiEAkhWDrap8G1x5mMSXJtdeJ56hx61G7sg4ojS+i4eabF4=
                                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Funnily enough, you can even tell that something is fishy through the base64, with the abnormal repetition over almost half of the signature.

## Recovering the secret nonce and private key

As Wikipedia explains, from a pair of colliding signatures `(r,s)` and `(r,s')`, we can recover `k` by computing

    k = (s - s') / (z - z')

Recall that all these numbers are elements of the integers modulo `n`, where `n` is the order of the generated subgroup on the curve. The `z` and `z'` are computed
from the hash of the message to be signed.

Here we hit our first problem: nowhere it is specified which hash algorithm to use. But since the subgroup order is a 256-bit number, it seems natural to use
a hash function with a 256-bit output, so SHA-256 is our prime candidate.

We can quickly test this hypothesis by doing a signature verification. Let us implement the verification algorithm in Haskell, and test it on our sample message
(i'm only showing the core parts, the full code can be found at the end of this article.


    verify :: Parameters -> Pubkey -> Signature -> Message -> Either String ()
    verify (ec, g, n) pub (r,s) m = do
        not (ison ec pub) ?? "public key not on curve"
        zero pub ?? "public key is zero"
        (not.zero) (pmul ec pub n) ?? "public key not in subgroup"
        not ((r `within` (0,n)) && (s `within` (0,n))) ?? "signature out of bounds"
        let z = expand (hash m)
            w = inv n s
            (u1,u2) = ((z*w) `mod` n, (r*w) `mod` n)
            o = padd ec (pmul ec g u1) (pmul ec pub u2)
        zero o ?? "validation point was zero"
        let (x1,_) = affine ec o
        ((x1 `mod` n) /= r) ?? "signature incorrect"


	curve = standard p256
    pub = ECPp 0xa6e5edc5154ceba06cd30a28ab6f3c1b755750796b6c54e431d6c533e49561a1 0x7249fc948201704cd2a20ee4dac8ea4b40d17aca96a953779706722459d72a4b 1
    r = 0x3CDD8BCF5B734DA67714F14A8EED03C766AF75E5D0FAF1BA04B2ECA3BDDCD47A
    s1 = 0x2B1371F2F8D3C3DC0604B994D0CBBBE3CC75522CAD18B1B1283CB6516672377C
    m1 = BS8.pack "he signed data). These assuran"
    s2 = 0x921583ADAA7C1B5C7998C49726D75E279EA1C7AD46EEC838A234BE8B879A6C5E
    m2 = BS8.pack "ture verification process. A s"



    > verify curve pub (r,s1) m1
    True
    > verify curve pub (r,s2) m2
    True

	

Incredibly, it works, both signatures check out. After testing that fake signatures fail too (for instance by swapping m1 and m2), we can now be sure that
our choice of hash function was correct, and that everything is working correctly.
	
Let us then recover the nonce:

	crack :: Parameters -> Pubkey -> (Message, Signature) -> (Message, Signature) -> Either String (Nonce, Privkey)
    crack p@(ec, g, n) pub (m,(r,s)) (m', (r',s')) = do
        (r /= r') ?? "Sorry, signatures must have identical k for attack to work"
        verify p pub (r,s) m
        verify p pub (r,s') m'
        let (z, z') = (expand (hash m), expand (hash m'))
            k = (((z - z') `mod` n) * inv n ((s - s') `mod` n)) `mod` n
            d = (((s*k - z) `mod` n) * inv n r) `mod` n
        return (k,d)

    > crack curve pub (m1, (r,s1)) (m2, (r,s2))
	Right (4242,103872287559379399914744843410101948027129342521289341348401895871744811275392)
    	
The attack succeeded, and we recovered the nonce `k` along the private key `d`. We can see that the `k` is way too small; With minimal effort, 
we could have also recovered it from a single signature, by using the baby-step giant-step algorithm to compute the discrete logarithm of r.
Or even bruteforce, with such a small `k`.


## Forging the signature

Translating the signature algorithm to Haskell:

    sign :: Parameters -> Privkey -> Message -> IO Signature
    sign p@(_,_,n) d m = go where
        z = expand (hash m)
        sign' = signDeterministic p d z
        go = do
            k <- randomRIO (1,n-1)
            let (r,s) = sign' k
           if r == 0 || s == 0
                then go
                else return (r,s)

    signDeterministic :: Parameters -> Privkey -> Integer -> Nonce -> Signature
    signDeterministic (ec, g, n) d z k = (r,s) where
        o = pmul ec g k
        (x1,_) = affine ec o
        r = x1 `mod` n
        s = ((z + r*d) * (inv n k)) `mod` n


The main signature algorithm consists of repeatedly choosing random values for `k`, and perform the deterministic
signature algorithm, until the signature suceeds. Separating the deterministic part of the aglorithm allows us to check
that we can reproduce the existing signatures correctly:

    > signDeterministic curve d (expand (hash m1)) k
    (27530209049394021804796111372881947298263230630819314890086433009851116082298,
     19483809031160088219707292315523236671341089479317580677415257951387180480380)

Those are the same values we had for our first colliding signature, so we are indeed able to forge signatures. Now to forge a valid signature for the target message:


    > let target = BS8.pack "Please give me the flag"
    > signature <- sign curve d target
    > signature
    (49271142319910802430075384114425720548318215767445215127383189594429821860418,
    96491998978165891981048277068100550839827797802373671138054367991983326982329)

And we have a valid signature. All that remains is to put it in the proper format. Thankfully, DER is not that hard. Let's have a look at the DER encoding of the first signature, and compare it with the ASN.1 parser output:

    $ openssl asn1parse <<< MEQCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiArE3Hy+NPD3AYEuZTQy7vjzHVSLK0YsbEoPLZRZnI3fA==
        0:d=0  hl=2 l=  68 cons: SEQUENCE          
        2:d=1  hl=2 l=  32 prim: INTEGER           :3CDD8BCF5B734DA67714F14A8EED03C766AF75E5D0FAF1BA04B2ECA3BDDCD47A
       36:d=1  hl=2 l=  32 prim: INTEGER           :2B1371F2F8D3C3DC0604B994D0CBBBE3CC75522CAD18B1B1283CB6516672377C
    
    $ base64 -d <<< MEQCIDzdi89bc02mdxTxSo7tA8dmr3Xl0PrxugSy7KO93NR6AiArE3Hy+NPD3AYEuZTQy7vjzHVSLK0YsbEoPLZRZnI3fA== |hexdump -C
    00000000  30 44 02 20 3c dd 8b cf  5b 73 4d a6 77 14 f1 4a  |0D. <...[sM.w..J|
    00000010  8e ed 03 c7 66 af 75 e5  d0 fa f1 ba 04 b2 ec a3  |....f.u.........|
    00000020  bd dc d4 7a 02 20 2b 13  71 f2 f8 d3 c3 dc 06 04  |...z. +.q.......|
    00000030  b9 94 d0 cb bb e3 cc 75  52 2c ad 18 b1 b1 28 3c  |.......uR,....(<|
    00000040  b6 51 66 72 37 7c                                 |.Qfr7||
    00000046

DER is a type-length-value encoding. In the hexdump, we can see the tag for `SEQUENCE` (`0x30`), followed by a payload of 68 (0x44) bytes. The first element is an `INTEGER` (`0x02`) of 32 bytes (0x20), the second element is the same. Since we are not changing the size of the signature, we can simply graft its bytes with the appropriate
headers:

    wrap :: Signature -> BS.ByteString
    wrap (r,s) = B64.encode $ BS.concat [ BS.pack [0x30, 0x44, 0x02, 0x20]
                                        , unexpand r
                                        , BS.pack [0x02, 0x20]
                                        , unexpand s
                                        ]



    > wrap signature
    "MEQCIHezKnsrkDZKoe28ZjyUecU+V/VZG5jU0OAaPr973u96AiBwB4imIDh7eYCvlwYrchiAADEWNEOGtrR6om1dvsuqTw=="

We submit as a final solution:

    'Please give me the flag'   MEQCIHezKnsrkDZKoe28ZjyUecU+V/VZG5jU0OAaPr973u96AiBwB4imIDh7eYCvlwYrchiAADEWNEOGtrR6om1dvsuqTw==


[1]: https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm
[2]: https://tools.ietf.org/html/rfc5480
