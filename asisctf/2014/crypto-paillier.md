# ASIS-CTF 2014: Crypto: Paillier

En donnée, on nous fournit l'addresse du service suivant:

    max@truite ~ $ nc -v asis-ctf.ir 12445
    DNS fwd/rev mismatch: asis-ctf.ir != mail.depository.ir
    asis-ctf.ir [87.107.124.12] 12455 (?) open

            Here we use a well-known cryptosystem, which introduced in late 90s as a part of PhD 
            Thesis. This cryptosystem is a probabilistic asymmetric algorithm, so computer nerds 
            are familiar with the basics. The power of this cryptosystem is based on the fact that 
            no efficient general method for computing discrete logarithms on conventional computers 
            is known. In real world it could be used in a situation where there is a need for 
            anonymity and a mechanism to validate, like election.

        What's the name of this cryptosystem? 

Après quelques essais, on trouve Paillier:
    
        What's the name of this cryptosystem? 
    Paillier 
    The secret is: 9875676257636701658620619485901408458156381957610287297432150752657594971112130734695398259742040350122954870324237948599808827532539278700745263553319482092460456957407527479335203333233299470927024366020632206967357797846981812988215039671606873392079187791573839733015708764105651394898965004633566072121653336961074172004673994159863360102994472700677843818502473936852657203606418773655065969394463059460646887148864238467101809097431545413094791408119903360268021677565512905315679155054822925595572277268025072732035284201497048421809084512809302973116027126313140282915561007559382521979998979794092988861921 
    
    Tell us your choise:
    ------------------------ 
    [E]ncrypt: [D]ecrypt:  


Le nom du système est donc le bon. Nous avons une valeur secrète, un nombre en décimal, et apparemment la possibilité d'utiliser le service comme oracle, sans disposer directement de la clef.

Le service accepte de déchiffrer des valeurs abritraires, mais pas la fameuse valeur secrète:

    Tell us your choise: 
    ------------------------ 
    [E]ncrypt: [D]ecrypt: D  
    Tell us your secret to decrypt: 98756 
    Your original message is: 950874...........209298 
    [E]ncrypt: [D]ecrypt: D
    Tell us your secret to decrypt: 987567..........861921
    Don't fool me! X-(

(J'ai raccourci les grands nombres par souci de lisibilité, mais le service donne les nombres complets)

La caractéristique distinctive du cryptosystème de Paillier réside dans ses propriétés homomorphiques. Si, par exemple, on à 3 messages clairs m, m_1 et m_2 tels que

m = m_1 + m_2 (mod n)

il est possible de calculer un texte chiffré c correspondant au message m, sans connaitre m_1 et
m_2, en prenant

c = c_1 * c_2 (mod n²)

Ici, notre objectif va donc être de retrouver le message m de notre secret, sans procéder à son déchiffrement. Pour ceci, nous allons d'abord trouver un c_1 et un c_2 acceptables, puis les déchiffrer,
et il ne nous restera plus qu'a les additionner (mod n) pour retrouver le message original.

En supposant que le message m a été choisi arbitrairement, sans rechercher une valeur particulière de c, c est uniformément distribué dans le groupe multiplicatif M(n²), il est donc hautement probable
qu'il contienne des petits facteurs. Essayons de trouver un petit facteur, avec haskell, par une technique tout à fait rudimentaire:

    Prelude> let c = 98756762576...92988861921
    Prelude> head [ k | k <- [2..], c `mod` k == 0 ]
    11

On identifie presque immédiatement le petit facteur 11, et on calcule son cofacteur par division:

    Prelude> c `div` c1
    8977887.........362623811
    
On soumet alors les deux valeurs c1 et c2 à notre oracle:
    Tell us your choise: 
    ------------------------
    [E]ncrypt: [D]ecrypt: d
    Tell us your secret to decrypt: 11
    Your original message is: 151709608361226950608367113680465803878157243458154889691251326923018155715697619180502339981181175975825978824071269220455262079491432880547349570206488156562505637347940621075801863098020222566004446665582027684319850545795810085447457566869848890807713892527339364953877439451805024781681882111584734863530
    Tell us your choise: 
    ------------------------
    [E]ncrypt: [D]ecrypt: d 
    Tell us your secret to decrypt: 89778875....23811
    Your original message is: 6242769198942584817411105473450672386047972883716325422178669503309780681241088351102877529576142539995828596461517120317457326548163994292246457822325179469736425807552956065728181142742368861833271780719984831097410099764709060287670942937998909474785496814133308188930429303413286386679766196777006675616


On repasse ces messages dans Haskell:

    Prelude> let m1 = 15170....863530
    Prelude> let m2 = 62427....675616

Problème: nous savons maintenant que m = m1 + m2 (mod n), mais nous ne connaissons pas n. Comment le trouver ? En exploitant la propriété homorphique pour créer des valeurs équivalentes mod n, et en regardant leur hypothétique différence.

Par exemple, si on génère au hasard un texte chiffré c_a, et qu'on soumet à l'oracle c_a, puis c_a², 
on obtiendra en retour deux valeurs m_a et m_2a telles que m_2a = 2 m_a (mod n); si on calcule
x = m_2a - 2 m_a, x sera un multiple de n.

On peut faire le test avec quelques paires de valeurs simples: 2 et 4, 3 et 9, 5 et 25... coup de chance, le premier essai nous révèle immédiatement la valeur

    157952377560169535425778219153916476264205216341871215113429996426327936396938707531605217510757318515821807420532786340772719406039596874839596028028813336032242063155493577141530044240762591427837718446302012515417260613072710825491978074491263004126928295563734080003249704892308810330085722662911791521557

Dont la taille est relativement proche du n recherché. On vérifie si cela est suffisant pour déchiffrer:

    Prelude> let n = 157952...521557
    Prelude> let m = (m1 + m2) `mod` n
    Prelude> m
    32487808320243150435316584796155571093777738593139558163862909500838275925645449950017589

Cette valeur est beaucoup plus petite que n, il est donc hautement probable qu'il s'agisse du bon
message, sans padding. Mais comment l'interpréter ?

    Prelude> import Numeric
    Prelude Numeric> showHex m []
    "415349535f3835633966656264346331353935306162316631396136626437613934663835"

Voila qui ressemble fortement à du décimal, affichons le en ascii:

    Prelude Numeric> import qualified Data.ByteString as BS
    Prelude Numeric BS> BS.reverse $ BS.unfoldr (\x -> if x == 0 then Nothing else Just (fromIntegral (x `mod` 256), x `div` 256)) m 
    "ASIS_85c9febd4c15950ab1f19a6bd7a94f85"



