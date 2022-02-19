From ./scripts/run-doc-server.sh in go-mcl file

func G1LagrangeInterpolation(out *G1, xVec []Fr, yVec []G1) error
    G1LagrangeInterpolation --

func G1Mul(out *G1, x *G1, y *Fr)
    G1Mul --

func G1MulCT(out *G1, x *G1, y *Fr)
    G1MulCT -- constant time (depending on bit lengh of y)

func G1MulVec(out *G1, xVec []G1, yVec []Fr)
    G1MulVec -- multi scalar multiplication out = sum mul(xVec[i], yVec[i])

func G1Neg(out *G1, x *G1)
    G1Neg --

func G1Normalize(out *G1, x *G1)
    G1Normalize --

func G1Sub(out *G1, x *G1, y *G1)
    G1Sub --

func G2Add(out *G2, x *G2, y *G2)
    G2Add --

func G2Dbl(out *G2, x *G2)
    G2Dbl --

func G2EvaluatePolynomial(y *G2, c []G2, x *Fr) error
    G2EvaluatePolynomial -- y = c[0] + c[1] * x + c[2] * x^2 + ...

func G2LagrangeInterpolation(out *G2, xVec []Fr, yVec []G2) error
    G2LagrangeInterpolation --

func G2Mul(out *G2, x *G2, y *Fr)
    G2Mul --

func G2MulVec(out *G2, xVec []G2, yVec []Fr)
    G2MulVec -- multi scalar multiplication out = sum mul(xVec[i], yVec[i])

func G2Neg(out *G2, x *G2)
    G2Neg --

func G2Normalize(out *G2, x *G2)
    G2Normalize --

func G2Sub(out *G2, x *G2, y *G2)
    G2Sub --

func GTAdd(out *GT, x *GT, y *GT)
    GTAdd --

func GTDiv(out *GT, x *GT, y *GT)
    GTDiv --

func GTInv(out *GT, x *GT)
    GTInv --

func GTMul(out *GT, x *GT, y *GT)
    GTMul --

func GTNeg(out *GT, x *GT)
    GTNeg --

func GTPow(out *GT, x *GT, y *Fr)
    GTPow --

func GTSub(out *GT, x *GT, y *GT)
    GTSub --

func GetCurveOrder() string
    Returns the order of G1 as a base 10 string

func GetFieldOrder() string
    GetFieldOrder -- return the characteristic of the field where a curve is
    defined

func GetFpByteSize() int
    GetFpByteSize -- the serialized size of Fp

func GetFpUnitSize() int
    GetFpUnitSize -- same as GetMaxOpUnitSize()

func GetFrByteSize() int
    GetFrByteSize -- the serialized size of Fr

func GetFrUnitSize() int
    GetFrUnitSize --

func GetG1ByteSize() int
    GetG1ByteSize -- the serialized size of G1

func GetG2ByteSize() int
    GetG2ByteSize -- the serialized size of G2

func GetMaxOpUnitSize() int
    GetMaxOpUnitSize --

func GetOpUnitSize() int
    GetOpUnitSize -- the length of Fr is GetOpUnitSize() * 8 bytes

func GetUint64NumToPrecompute() int
    GetUint64NumToPrecompute --

func InitFromString(curveStr string)
    Call this function before calling all the other operations. This function is
    not thread safe. 'curve' can be 'bn254', 'bn254_snark', 'fp382-1', 'fp382-2'
    or 'bls12-381', but the current library is linked with mcl in such a way
    that only 'bn254', 'bn254_snark' and 'bls12-381' are supported.

func InitMclHelper(curve int)
func MapToG1(out *G1, x *Fp) error
    MapToG1 --

func MapToG2(out *G2, x *Fp2) error
    MapToG2 --

func MillerLoop(out *GT, x *G1, y *G2)
    MillerLoop --

func MillerLoopVec(out *GT, xVec []G1, yVec []G2)
    MillerLoopVec -- multi pairings ; out = prod_i e(xVec[i], yVec[i])

func Pairing(out *GT, x *G1, y *G2)
    Pairing --

func PrecomputeG2(Qbuf []uint64, Q *G2)
    PrecomputeG2 --

func PrecomputedMillerLoop(out *GT, P *G1, Qbuf []uint64)
    PrecomputedMillerLoop --

func PrecomputedMillerLoop2(out *GT, P1 *G1, Q1buf []uint64, P2 *G1, Q2buf []uint64)
    PrecomputedMillerLoop2 --

func SetETHserialization(enable bool)
    SetETHserialization --

func SetMapToMode(mode int) error
    SetMapToMode --

func SupportsRootsOfUnity() bool
func VerifyOrderG1(doVerify bool)
    VerifyOrderG1 -- verify order if SetString/Deserialize are called

func VerifyOrderG2(doVerify bool)
    VerifyOrderG2 -- verify order if SetString/Deserialize are called


TYPES

type Fp struct {
        // Has unexported fields.
}
    Fp --

func (x *Fp) Clear()
    Clear --

func (x *Fp) Deserialize(buf []byte) error
    Deserialize --

func (x *Fp) GetString(base int) string
    GetString --

func (x *Fp) IsEqual(rhs *Fp) bool
    IsEqual --

func (x *Fp) IsNegative() bool
    IsNegative -- true if x >= (p + 1) / 2

func (x *Fp) IsOdd() bool
    IsOdd --

func (x *Fp) IsOne() bool
    IsOne --

func (x *Fp) IsValid() bool
    IsValid --

func (x *Fp) IsZero() bool
    IsZero --

func (x *Fp) Random()
    Random --

func (x *Fp) Serialize() []byte
    Serialize --

func (x *Fp) SetBigEndianMod(buf []byte) error
    SetBigEndianMod --

func (x *Fp) SetByCSPRNG()
    SetByCSPRNG --

func (x *Fp) SetHashOf(buf []byte) bool
    SetHashOf --

func (x *Fp) SetInt64(v int64)
    SetInt64 --

func (x *Fp) SetLittleEndian(buf []byte) error
    SetLittleEndian --

func (x *Fp) SetLittleEndianMod(buf []byte) error
    SetLittleEndianMod --

func (x *Fp) SetString(s string, base int) error
    SetString --

type Fp2 struct {
        D [2]Fp
}
    Fp2 -- x = D[0] + D[1] i where i^2 = -1

func (x *Fp2) Clear()
    Clear --

func (x *Fp2) Deserialize(buf []byte) error
    Deserialize --

func (x *Fp2) IsEqual(rhs *Fp2) bool
    IsEqual --

func (x *Fp2) IsOne() bool
    IsOne --

func (x *Fp2) IsZero() bool
    IsZero --

func (x *Fp2) Serialize() []byte
    Serialize --

type Fr struct {
        // Has unexported fields.
}
    Fr --

func BigIntToFr(b *big.Int) *Fr
    Converts a big.Int to an Fr

func FrModExp_Slow(base *Fr, exp *Fr) *Fr
    mcl does not provide a function to exponentiate Fr's, which we need when
    randomly picking generators of G_{r-1}. Thus, we implement it here (slowly)
    via Go's big.Int.

func GetRootOfUnity() Fr
    Returns a primitive nth root of unity in Fr (assuming it supports one) Here,
    g is a generator of G_{r-1} and r1 is r-1.

func GetRootOfUnityFromGen(gen *Fr, n *Fr) Fr

func RandomFieldGenerator() Fr
    Returns the generator of the multiplicative subgroup of order r-1 of the
    field Fr

func (x *Fr) Clear()
    Clear --

func (x *Fr) Deserialize(buf []byte) error
    Deserialize --

func (x *Fr) GetString(base int) string
    GetString --

func (x *Fr) IsEqual(rhs *Fr) bool
    IsEqual --

func (x *Fr) IsNegative() bool
    IsNegative -- true if x >= (r + 1) / 2

func (x *Fr) IsOdd() bool
    IsOdd --

func (x *Fr) IsOne() bool
    IsOne --

func (x *Fr) IsValid() bool
    IsValid --

func (x *Fr) IsZero() bool
    IsZero --

func (x *Fr) Random()
    Random --

func (x *Fr) Serialize() []byte
    Serialize --

func (x *Fr) SetBigEndianMod(buf []byte) error
    SetBigEndianMod --

func (x *Fr) SetByCSPRNG()
    SetByCSPRNG --

func (x *Fr) SetHashOf(buf []byte) bool
    Assuming this hashes the specified buffer to a field element.

func (x *Fr) SetInt64(v int64)
    SetInt64 --

func (x *Fr) SetLittleEndian(buf []byte) error
    SetLittleEndian --

func (x *Fr) SetLittleEndianMod(buf []byte) error
    SetLittleEndianMod --

func (x *Fr) SetString(s string, base int) error
    SetString --

func (x *Fr) ToBigInt() *big.Int
    Converts an Fr to a big.Int

type G1 struct {
        X Fp
        Y Fp
        Z Fp
}
    G1 --

func (x *G1) Clear()
    Clear --

func (x *G1) Deserialize(buf []byte) error
    Deserialize --

func (x *G1) DeserializeUncompressed(buf []byte) error
    DeserializeUncompressed -- x.Deserialize() + y.Deserialize()

func (x *G1) GetString(base int) string
    GetString --

func (x *G1) HashAndMapTo(buf []byte) error
    HashAndMapTo --

func (x *G1) IsEqual(rhs *G1) bool
    IsEqual --

func (x *G1) IsValid() bool
    IsValid --

func (x *G1) IsValidOrder() bool
    IsValidOrder --

func (x *G1) IsZero() bool
    IsZero --

func (g *G1) Mul(y *Fr)

func (x *G1) Random()
    Randomly picks an element in G1 by hashing enough bytes from crypto/rand to
    the group G1.

func (x *G1) Serialize() []byte
    Serialize --

func (x *G1) SerializeUncompressed() []byte
    SerializeUncompressed -- all zero array if x.IsZero()

func (x *G1) SetString(s string, base int) error
    SetString --

type G2 struct {
        X Fp2
        Y Fp2
        Z Fp2
}
    G2 --

func (x *G2) Clear()
    Clear --

func (x *G2) Deserialize(buf []byte) error
    Deserialize --

func (x *G2) DeserializeUncompressed(buf []byte) error
    DeserializeUncompressed -- x.Deserialize() + y.Deserialize()

func (x *G2) GetString(base int) string
    GetString --

func (x *G2) HashAndMapTo(buf []byte) error
    HashAndMapTo --

func (x *G2) IsEqual(rhs *G2) bool
    IsEqual --

func (x *G2) IsValid() bool
    IsValid --

func (x *G2) IsValidOrder() bool
    IsValidOrder --

func (x *G2) IsZero() bool
    IsZero --

func (g *G2) Mul(y *Fr)

func (x *G2) Random()
    Randomly picks an element in G2 by hashing enough bytes from crypto/rand to
    the group G2.

func (x *G2) Serialize() []byte
    Serialize --

func (x *G2) SerializeUncompressed() []byte
    SerializeUncompressed -- all zero array if x.IsZero()

func (x *G2) SetString(s string, base int) error
    SetString --

type GT struct {
        // Has unexported fields.
}
    GT --

func (x *GT) Clear()
    Clear --

func (x *GT) Deserialize(buf []byte) error
    Deserialize --

func (x *GT) GetString(base int) string
    GetString --

func (x *GT) IsEqual(rhs *GT) bool
    IsEqual --

func (x *GT) IsOne() bool
    IsOne --

func (x *GT) IsZero() bool
    IsZero --

annieulichney@Annies-MBP-3 go-mcl % ./scripts/run-doc-server.sh

You can access the docs at:
     http://localhost:6060/pkg/#thirdparty 

package mcl // import "github.com/alinush/go-mcl"


CONSTANTS

const BLS12_381 = C.MCL_BLS12_381
    BLS12_381 --

const CurveFp254BNb = C.mclBn_CurveFp254BNb
    CurveFp254BNb -- 254 bit curve

const CurveFp382_1 = C.mclBn_CurveFp382_1
    CurveFp382_1 -- 382 bit curve 1

const CurveFp382_2 = C.mclBn_CurveFp382_2
    CurveFp382_2 -- 382 bit curve 2

const CurveSNARK1 = C.mclBn_CurveSNARK1
    254-bit BN curve with support for roots of unity

const IO_EC_AFFINE = C.MCLBN_IO_EC_AFFINE
    IO_EC_AFFINE --

const IO_EC_PROJ = C.MCLBN_IO_EC_PROJ
    IO_EC_PROJ --

const IRTF = 5 /* MCL_MAP_TO_MODE_HASH_TO_CURVE_07 */
    IRTF -- for SetMapToMode

const IoSerializeHexStr = C.MCLBN_IO_SERIALIZE_HEX_STR
    IoSerializeHexStr --

const ZERO_HEADER = 1 << 6

FUNCTIONS

func FinalExp(out *GT, x *GT)
    FinalExp --

func Fp2Add(out *Fp2, x *Fp2, y *Fp2)
    Fp2Add --

func Fp2Div(out *Fp2, x *Fp2, y *Fp2)
    Fp2Div --

func Fp2Inv(out *Fp2, x *Fp2)
    Fp2Inv --

func Fp2Mul(out *Fp2, x *Fp2, y *Fp2)
    Fp2Mul --

func Fp2Neg(out *Fp2, x *Fp2)
    Fp2Neg --

func Fp2Sqr(out *Fp2, x *Fp2)
    Fp2Sqr --

func Fp2SquareRoot(out *Fp2, x *Fp2) bool
    Fp2SquareRoot --

func Fp2Sub(out *Fp2, x *Fp2, y *Fp2)
    Fp2Sub --

func FpAdd(out *Fp, x *Fp, y *Fp)
    FpAdd --

func FpDiv(out *Fp, x *Fp, y *Fp)
    FpDiv --

func FpInv(out *Fp, x *Fp)
    FpInv --

func FpMul(out *Fp, x *Fp, y *Fp)
    FpMul --

func FpNeg(out *Fp, x *Fp)
    FpNeg --

func FpSqr(out *Fp, x *Fp)
    FpSqr --

func FpSquareRoot(out *Fp, x *Fp) bool
    FpSquareRoot --

func FpSub(out *Fp, x *Fp, y *Fp)
    FpSub --

func FrAdd(out *Fr, x *Fr, y *Fr)
    FrAdd --

func FrDiv(out *Fr, x *Fr, y *Fr)
    FrDiv --

func FrEvaluatePolynomial(y *Fr, c []Fr, x *Fr) error
    FrEvaluatePolynomial -- y = c[0] + c[1] * x + c[2] * x^2 + ...

func FrInv(out *Fr, x *Fr)
    FrInv --

func FrLagrangeInterpolation(out *Fr, xVec []Fr, yVec []Fr) error
    FrLagrangeInterpolation --

func FrMul(out *Fr, x *Fr, y *Fr)
    FrMul --

func FrNeg(out *Fr, x *Fr)
    FrNeg --

func FrPow2(out *Fr, pow2 int)
    Returns n = 2^{pow}. Useful when working with roots of unity. TODO: could
    speed this up using squaring

func FrSqr(out *Fr, x *Fr)
    FrSqr --

func FrSquareRoot(out *Fr, x *Fr) bool
    FrSquareRoot --

func FrSub(out *Fr, x *Fr, y *Fr)
    FrSub --

func G1Add(out *G1, x *G1, y *G1)
    G1Add --

func G1Dbl(out *G1, x *G1)
    G1Dbl --

func G1EvaluatePolynomial(y *G1, c []G1, x *Fr) error
    G1EvaluatePolynomial -- y = c[0] + c[1] * x + c[2] * x^2 + ...

func G1LagrangeInterpolation(out *G1, xVec []Fr, yVec []G1) error
    G1LagrangeInterpolation --

func G1Mul(out *G1, x *G1, y *Fr)
    G1Mul --

func G1MulCT(out *G1, x *G1, y *Fr)
    G1MulCT -- constant time (depending on bit lengh of y)

func G1MulVec(out *G1, xVec []G1, yVec []Fr)
    G1MulVec -- multi scalar multiplication out = sum mul(xVec[i], yVec[i])

func G1Neg(out *G1, x *G1)
    G1Neg --

func G1Normalize(out *G1, x *G1)
    G1Normalize --

func G1Sub(out *G1, x *G1, y *G1)
    G1Sub --

func G2Add(out *G2, x *G2, y *G2)
    G2Add --

func G2Dbl(out *G2, x *G2)
    G2Dbl --

func G2EvaluatePolynomial(y *G2, c []G2, x *Fr) error
    G2EvaluatePolynomial -- y = c[0] + c[1] * x + c[2] * x^2 + ...

func G2LagrangeInterpolation(out *G2, xVec []Fr, yVec []G2) error
    G2LagrangeInterpolation --

func G2Mul(out *G2, x *G2, y *Fr)
    G2Mul --

func G2MulVec(out *G2, xVec []G2, yVec []Fr)
    G2MulVec -- multi scalar multiplication out = sum mul(xVec[i], yVec[i])

func G2Neg(out *G2, x *G2)
    G2Neg --

func G2Normalize(out *G2, x *G2)
    G2Normalize --

func G2Sub(out *G2, x *G2, y *G2)
    G2Sub --

func GTAdd(out *GT, x *GT, y *GT)
    GTAdd --

func GTDiv(out *GT, x *GT, y *GT)
    GTDiv --

func GTInv(out *GT, x *GT)
    GTInv --

func GTMul(out *GT, x *GT, y *GT)
    GTMul --

func GTNeg(out *GT, x *GT)
    GTNeg --

func GTPow(out *GT, x *GT, y *Fr)
    GTPow --

func GTSub(out *GT, x *GT, y *GT)
    GTSub --

func GetCurveOrder() string
    Returns the order of G1 as a base 10 string

func GetFieldOrder() string
    GetFieldOrder -- return the characteristic of the field where a curve is
    defined

func GetFpByteSize() int
    GetFpByteSize -- the serialized size of Fp

func GetFpUnitSize() int
    GetFpUnitSize -- same as GetMaxOpUnitSize()

func GetFrByteSize() int
    GetFrByteSize -- the serialized size of Fr

func GetFrUnitSize() int
    GetFrUnitSize --

func GetG1ByteSize() int
    GetG1ByteSize -- the serialized size of G1

func GetG2ByteSize() int
    GetG2ByteSize -- the serialized size of G2

func GetMaxOpUnitSize() int
    GetMaxOpUnitSize --

func GetOpUnitSize() int
    GetOpUnitSize -- the length of Fr is GetOpUnitSize() * 8 bytes

func GetUint64NumToPrecompute() int
    GetUint64NumToPrecompute --

func InitFromString(curveStr string)
    Call this function before calling all the other operations. This function is
    not thread safe. 'curve' can be 'bn254', 'bn254_snark', 'fp382-1', 'fp382-2'
    or 'bls12-381', but the current library is linked with mcl in such a way
    that only 'bn254', 'bn254_snark' and 'bls12-381' are supported.

func InitMclHelper(curve int)
func MapToG1(out *G1, x *Fp) error
    MapToG1 --

func MapToG2(out *G2, x *Fp2) error
    MapToG2 --

func MillerLoop(out *GT, x *G1, y *G2)
    MillerLoop --

func MillerLoopVec(out *GT, xVec []G1, yVec []G2)
    MillerLoopVec -- multi pairings ; out = prod_i e(xVec[i], yVec[i])

func Pairing(out *GT, x *G1, y *G2)
    Pairing --

func PrecomputeG2(Qbuf []uint64, Q *G2)
    PrecomputeG2 --

func PrecomputedMillerLoop(out *GT, P *G1, Qbuf []uint64)
    PrecomputedMillerLoop --

func PrecomputedMillerLoop2(out *GT, P1 *G1, Q1buf []uint64, P2 *G1, Q2buf []uint64)
    PrecomputedMillerLoop2 --

func SetETHserialization(enable bool)
    SetETHserialization --

func SetMapToMode(mode int) error
    SetMapToMode --

func SupportsRootsOfUnity() bool
func VerifyOrderG1(doVerify bool)
    VerifyOrderG1 -- verify order if SetString/Deserialize are called

func VerifyOrderG2(doVerify bool)
    VerifyOrderG2 -- verify order if SetString/Deserialize are called


TYPES

type Fp struct {
        // Has unexported fields.
}
    Fp --

func (x *Fp) Clear()
    Clear --

func (x *Fp) Deserialize(buf []byte) error
    Deserialize --

func (x *Fp) GetString(base int) string
    GetString --

func (x *Fp) IsEqual(rhs *Fp) bool
    IsEqual --

func (x *Fp) IsNegative() bool
    IsNegative -- true if x >= (p + 1) / 2

func (x *Fp) IsOdd() bool
    IsOdd --

func (x *Fp) IsOne() bool
    IsOne --

func (x *Fp) IsValid() bool
    IsValid --

func (x *Fp) IsZero() bool
    IsZero --

func (x *Fp) Random()
    Random --

func (x *Fp) Serialize() []byte
    Serialize --

func (x *Fp) SetBigEndianMod(buf []byte) error
    SetBigEndianMod --

func (x *Fp) SetByCSPRNG()
    SetByCSPRNG --

func (x *Fp) SetHashOf(buf []byte) bool
    SetHashOf --

func (x *Fp) SetInt64(v int64)
    SetInt64 --

func (x *Fp) SetLittleEndian(buf []byte) error
    SetLittleEndian --

func (x *Fp) SetLittleEndianMod(buf []byte) error
    SetLittleEndianMod --

func (x *Fp) SetString(s string, base int) error
    SetString --

type Fp2 struct {
        D [2]Fp
}
    Fp2 -- x = D[0] + D[1] i where i^2 = -1

func (x *Fp2) Clear()
    Clear --

func (x *Fp2) Deserialize(buf []byte) error
    Deserialize --

func (x *Fp2) IsEqual(rhs *Fp2) bool
    IsEqual --

func (x *Fp2) IsOne() bool
    IsOne --

func (x *Fp2) IsZero() bool
    IsZero --

func (x *Fp2) Serialize() []byte
    Serialize --

type Fr struct {
        // Has unexported fields.
}
    Fr --

func BigIntToFr(b *big.Int) *Fr
    Converts a big.Int to an Fr

func FrModExp_Slow(base *Fr, exp *Fr) *Fr
    mcl does not provide a function to exponentiate Fr's, which we need when
    randomly picking generators of G_{r-1}. Thus, we implement it here (slowly)
    via Go's big.Int.

func GetRootOfUnity() Fr
    Returns a primitive nth root of unity in Fr (assuming it supports one) Here,
    g is a generator of G_{r-1} and r1 is r-1.

func GetRootOfUnityFromGen(gen *Fr, n *Fr) Fr

func RandomFieldGenerator() Fr
    Returns the generator of the multiplicative subgroup of order r-1 of the
    field Fr

func (x *Fr) Clear()
    Clear --

func (x *Fr) Deserialize(buf []byte) error
    Deserialize --

func (x *Fr) GetString(base int) string
    GetString --

func (x *Fr) IsEqual(rhs *Fr) bool
    IsEqual --

func (x *Fr) IsNegative() bool
    IsNegative -- true if x >= (r + 1) / 2

func (x *Fr) IsOdd() bool
    IsOdd --

func (x *Fr) IsOne() bool
    IsOne --

func (x *Fr) IsValid() bool
    IsValid --

func (x *Fr) IsZero() bool
    IsZero --

func (x *Fr) Random()
    Random --

func (x *Fr) Serialize() []byte
    Serialize --

func (x *Fr) SetBigEndianMod(buf []byte) error
    SetBigEndianMod --

func (x *Fr) SetByCSPRNG()
    SetByCSPRNG --

func (x *Fr) SetHashOf(buf []byte) bool
    Assuming this hashes the specified buffer to a field element.

func (x *Fr) SetInt64(v int64)
    SetInt64 --

func (x *Fr) SetLittleEndian(buf []byte) error
    SetLittleEndian --

func (x *Fr) SetLittleEndianMod(buf []byte) error
    SetLittleEndianMod --

func (x *Fr) SetString(s string, base int) error
    SetString --

func (x *Fr) ToBigInt() *big.Int
    Converts an Fr to a big.Int

type G1 struct {
        X Fp
        Y Fp
        Z Fp
}
    G1 --

func (x *G1) Clear()
    Clear --

func (x *G1) Deserialize(buf []byte) error
    Deserialize --

func (x *G1) DeserializeUncompressed(buf []byte) error
    DeserializeUncompressed -- x.Deserialize() + y.Deserialize()

func (x *G1) GetString(base int) string
    GetString --

func (x *G1) HashAndMapTo(buf []byte) error
    HashAndMapTo --

func (x *G1) IsEqual(rhs *G1) bool
    IsEqual --

func (x *G1) IsValid() bool
    IsValid --

func (x *G1) IsValidOrder() bool
    IsValidOrder --

func (x *G1) IsZero() bool
    IsZero --

func (g *G1) Mul(y *Fr)

func (x *G1) Random()
    Randomly picks an element in G1 by hashing enough bytes from crypto/rand to
    the group G1.

func (x *G1) Serialize() []byte
    Serialize --

func (x *G1) SerializeUncompressed() []byte
    SerializeUncompressed -- all zero array if x.IsZero()

func (x *G1) SetString(s string, base int) error
    SetString --

type G2 struct {
        X Fp2
        Y Fp2
        Z Fp2
}
    G2 --

func (x *G2) Clear()
    Clear --

func (x *G2) Deserialize(buf []byte) error
    Deserialize --

func (x *G2) DeserializeUncompressed(buf []byte) error
    DeserializeUncompressed -- x.Deserialize() + y.Deserialize()

func (x *G2) GetString(base int) string
    GetString --

func (x *G2) HashAndMapTo(buf []byte) error
    HashAndMapTo --

func (x *G2) IsEqual(rhs *G2) bool
    IsEqual --

func (x *G2) IsValid() bool
    IsValid --

func (x *G2) IsValidOrder() bool
    IsValidOrder --

func (x *G2) IsZero() bool
    IsZero --

func (g *G2) Mul(y *Fr)

func (x *G2) Random()
    Randomly picks an element in G2 by hashing enough bytes from crypto/rand to
    the group G2.

func (x *G2) Serialize() []byte
    Serialize --

func (x *G2) SerializeUncompressed() []byte
    SerializeUncompressed -- all zero array if x.IsZero()

func (x *G2) SetString(s string, base int) error
    SetString --

type GT struct {
        // Has unexported fields.
}
    GT --

func (x *GT) Clear()
    Clear --

func (x *GT) Deserialize(buf []byte) error
    Deserialize --

func (x *GT) GetString(base int) string
    GetString --

func (x *GT) IsEqual(rhs *GT) bool
    IsEqual --

func (x *GT) IsOne() bool
    IsOne --

func (x *GT) IsZero() bool
    IsZero --

func (x *GT) Serialize() []byte
    Serialize --

func (x *GT) SetInt64(v int64)
    SetInt64 --

func (x *GT) SetString(s string, base int) error
    SetString --
