# zk-blind

post anonymous confessions about your work place in zero-knowledge!

`yarn` to install all dependencies.

## generate inputs

generate inputs into `jwt.json`
```
node scripts/generate_input.js
``` 

## circuits 

compile circuits in root project directory.
```
./shell_scripts/1_compile.sh
```

generate witness
```
./shell_scripts/2_gen_wtns.sh
```

generate chunked zkeys
```
./shell_scripts/3_gen_chunk_zkey.sh
```

phase 2 and getting full zkey + vkey
```
snarkjs groth16 setup ./build/jwt/jwt.r1cs ./circuits/powersOfTau28_hez_final_22.ptau ./build/jwt/jwt_single.zkey

snarkjs zkey contribute ./build/jwt/jwt_single.zkey ./build/jwt/jwt_single1.zkey --name="1st Contributor Name" -v

snarkjs zkey export verificationkey ./build/jwt/jwt_single1.zkey ./build/jwt/verification_key.json

```

generate proof
```
snarkjs groth16 prove ./build/jwt/jwt_single1.zkey ./build/jwt/witness.wtns ./build/jwt/proof.json ./build/jwt/public.json
```

verify proof
```
snarkjs groth16 verify ./build/jwt/verification_key.json ./build/jwt/public.json ./build/jwt/proof.json
```



