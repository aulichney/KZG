## Notation

The elliptic equation of a curve E is E: y^2 = x^3 + b.

- Fp ; a finite field of a prime order p, where a curve is defined over.
- Fr ; a finite field of a prime order r.
- Fp2 ; the field extension over Fp with degree 2. Fp[i] / (i^2 + 1).
- Fp6 ; the field extension over Fp2 with degree 3. Fp2[v] / (v^3 - Xi) where Xi = i + 1.
- Fp12 ; the field extension over Fp6 with degree 2. Fp6[w] / (w^2 - v).
- G1 ; the cyclic subgroup of E(Fp).
- G2 ; the cyclic subgroup of the inverse image of E'(Fp^2) under a twisting isomorphism from E' to E.
- GT ; the cyclic subgroup of Fp12.
- G1, G2, and GT have the order r.

The pairing e: G1 x G2 -> GT is the optimal ate pairing.

mcl treats G1 and G2 as an additive group and GT as a multiplicative group.

mclSize ; unsigned int if WebAssembly else size_t
