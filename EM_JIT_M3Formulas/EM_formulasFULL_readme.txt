1. Instalation
2. Version history
3. Sites and wishes
4. Organisation of Formulas
5. Explanation of Formulas
6. Example parameters
7. Mathematics

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
By Edgar Malinovsky
Use these algorithms as and where you wish as long as you give proper credits. 

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

1. Instalation:

Just put them in M3Formulas directory


  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *


2. Version history


Version 1.3:
Added formulas:
+ JIT_EM_N_ElazoBulb.m3f
+ JIT_EM_N_KalezoBox.m3f
+ JIT_EM_U_Superseed_Lp.m3f
Chudobox, Domofractal, FLD_Boxbulb - added internal conditionals to speed up calculation with default values:
vBenesiROtation =0; Thickness = 0; Power_ =2. No noticable differences of rendering.
(all are marked with version 1.3)

Version 1.2:
Updated:
JIT_EM_N_ChudoBox.m3f	+ BtoMag rotation and free folding
JIT_EM_Transf_Fisheye2.m3f  + full 4D	
JIT_EM_Transf_Fisheye8.m3f  + full 4D
JIT_EM_U_Techna_transform.m3f + completely different transformation which now actualy works.
JIT_EM_N_BoxBulb.m3f , JIT_EM_Fld_BoxBulb.m3f slightly less boxed but cleaner pow4 modulus shape.
New:
+ JIT_EM_FLDmbrot_Xamari.m3f
+ JIT_EM_FLDmset_Naridar.m3f
+ JIT_EM_Fld_PilarsOfKhwarezmi.m3f

These are marked with Version 1.2 All others should be marked with "Formula version 1.1" or else it is an older version from older packages.

Full package of formulas. Changes: improved math - generates faster, all FLDs expanded - larger variety of scenery, corrected mistakes of chudobox spherefold and techna transformation. + formula Domofractal with it's own explanation.

Variable Addition of old version of FLDs corespond to four: AdditionX , AdditionY, AdditionZ AdditionW. To keep compatibility with previous saves one of these is in position of former variable and others are placed at the bottom. The same goes for expanded folds
 

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

3. Sites and wishes


Original upload thread with the latest versions and some pics is here (until that site is locked):
http://www.fractalforums.com/mandelbulb-3d/em-formulas-for-mandelbulb3d/
(github could had older version of this)


If you had made something good out of this I WANT TO SEE IT. 
So please share it here:
http://edo555.deviantart.com/ 

I don't use that site often but I would like to see the pictures of these formulas. That would be impossible if you aren't active watcher. It is alsou the only profit I can get from this work.

I made a thread for this purpose but the site soon will be turned into archive:
http://www.fractalforums.com/gallery/em-formulas-for-mandelbulb3d-pictures/



  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *


4. Organisation of Formulas



Formulas are organised as folows:

_Fld_ - 3D space folding formulas. 

_N_ - "Normal" Mandelbrot like formulas and some boxes. 

_Transf_ - Transformations is like _formulas in Ads. 

JIT_EM_NOTHING.m3f - The most important formula ever. Does absolutely nothing.

_U_ - Unusual "strange" formulas which may not be good for general fractaling. 



  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *


5. Explanation of Formulas





The most usefull of these could be the FLDs and Domofractal - fractal based house generator, maybe the chududobox and the more later formulas of versions 1.2 and 1.3.

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

FLDs - Algebraic Space Fold.

All Fld-s is like follows:
Initialisation with x,y,z pixel values
iteration start:

Integer based folding of space.
Scaleing by factor.
Julia set like addition of some number or not.
Raising in power - movement in 3D space.

This type came out from 2 sources. 1st, I wanted to make something simmilar to Folding int Pow and the 2nd, the lack of the knowledge of M3D language as catalisator.
These formulas combines readily, but woun't generate julia sets as they depends only on initial pixel values.


Variables:  
Fold - integer only: 1, 2, 3, ... Fractional numbers is rounded by formula. Or else symmetry brakeing will go wrong.

AdditionX, Y Z W - analog of julia values. They are divided for compatibility reasons.

Scale - as in simmilar formulas.

Addition X,Y,Z,W =0, Fold = 0, Scale = 1 together with _addC will bring up original bulb/brot fractal. Hovewer the most symmetric folding multiplications alone won't generate fractals at all.

All these have the same general structure and if one of formula generated fractal in certain zoom, all other FLDs and their hybrids should too. It is usefull as zooms of these have richer shapes than in default wiev. 

Maybe Newtonian Triples power 3 and Hypercomplex crystal is best FLDS. But saturns alsou is pretty cool.


FLDmbrot
JIT_EM_FLDmbrot_Xamari.m3f and JIT_EM_FLDmset_Naridar.m3f are strechless mandelbrot set expansion of these FLDs. First one is pow2 quaternion, the second calculates pow2 quaternion and hypercomplex tricorn and then choses witch is the largest, hence more weird. Cutting scale 1 fractals will bring up 2D mandelbrot, tricorn or burning ship fractals. These will generate julia sets


  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

N_ (normal) formulas

Chudobox - basicaly generates storehouse like scenery. With Benesi rotation it will generate naturalistic rock shapes. 0 - no effect, 1 - one rotation just like of BRotateToMag. Rotation is fixed, values between 0 and 1 is just interpolated. 
Fish eye variable works in inverse direction, the less the value the stronger is an effect hence antiFIsheye. It distorts and sometimes solidifies fractal. Put some 5000 and it will have no effect.
Fold is free in each axis and with FoldZ = 0 formula is mutch like Amazing Surface fractal.


Newtonian Triplets is not very usefull alone. But could introduce drum like shape on hybridisation. They are included becouse of "mathematical beauty".


HyperTricorn - grailish tricorn fractal conj(z^2) +c of 4D hypercomplex numbers. Looks like built in mandelbulb based tricorn fractal but with different small features. In cutouts there are mandelbrot and tricorn fractals.

MbrotQm4D - in zooms on bulbs it shows some small mandelbrots and threads mutch like 2D mandelbrot set.

Domofractal - house generator with it's own explanation.



Kalezobox and Elazobulb - came form two sources, http://gannjondal.deviantart.com/ formula tutorials and mathematics of Lp spaces. 
These are "smart" formulas. If all curvatures is equal it awoyds some slow functions, and for 1 1 1 or 2 2 2 it uses simpler formulas.  
Formula will use only integer values as sCurvatures. That is done becouse of speed concerns.

sCurvature = p = 1 is "diamond" or square, of p = 2 is normal spherical radius and p = 4 is streamlined cell phone shape.

 



Elazobulb - uses idea from JIT_gnj_TwoRealPower_02.m3f of calculateing in paralel two mandelbulbs of different powers and then puting them together. If one bulb has positive power and another negative resulting bulb is very elaborate with lot of holes. Bulbs are interpolated (ratio) between 0 and 1 and beyond these points. If both bulbs have the same power "smart" formula avoids calculation of same thing twice. 

Changed sCurvature can get rid of messy stretch at the mandelbulb poles. p=1 will add certain stretchy angles. Jet some of combinations of x,y,z sCurvatures will ruin fractal. x=y=z allways will generate some mandelbulb and is less prone to noise.


KalezoBox - a simplification, then correction and modification of Amazing/mandelBox from gannjondal formulas. It is a box with just sphere inversion between two Radiuses but in LP spaces and the C is added descaled. 
Some of this modification was just becouse example Amazing box were slightly noisy.
Just like AmazingBox it could be hybridised with _rotation. It is mutch more different than most of variations on Abox.


  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

Transformations
Formulas is simmilar to flame fractal Fish Eye transformation. Power 2 fish eye will introduce some roundness and cartoony feel to just everything. Power 8 - pillow shape. Simmilar to negative value _asdam transformation. 
Decreasing transformation factor will increse its strenght. 

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

U_nusual formulas
These could make some interesting things and shows side effects of DE raymarcher but could have some problems so they aren't N. 

Swirls - create interesting interference pictures on far zooms. Is it side effect of 3D raymarching?  
Gilgamesh Head - have cool shape jet it can't create mutch more than it. And becouse of how it is implemented it woun't hybridise in Alternate or create julia sets.

Techna transformation - in version 1.2 now it actualy works but is completely different transformation. It can give the Mandelbul a plastic flooks, but then Strenght Vector must be <-2 or >2 . The effect is linear between 0 - no effect on fractal and 1 - generates only the unit cube. Now it is not U - it is problemless.

Superseed_Lp - I used it to explore Lp spaces with different p along dimensions. Shape is pretty cool but is too simple and not the fractal. It can work as Fish Eye transformations but with more variables. It would be better as difs hence is rated U.


  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *


6. Example parameters




I used some of these copy-past saves to test these formulas. Most are just examples not artwork. 
Formulas Version 1.1 parameters:


1. 
FLD example. All other FLDs and their hybrids will generate here something:

Mandelbulb3Dv18{
g....kQ...UG/...w....EA..AkDMqPPVb6mzQuCe17dV./Er1N4ILZ6QzvqKfGW90Y/.hgzenP.R7xD
................................uqFfK3Eg2/2........A./.........E........y.2...wD
...Uz6/..........E.0/.....Uh....j....2E4.....gO/o/JqYplD/.kmEwME...m/xa21g1....U
z.....kD12../.Uo5zfqrOogzOAshklLzL.EJbULK34c3z1...........U0.....y1...sD...../..
.w1...kDrgRXgaKJPwvIPosFfqK/zcABA0LgJQhDYhp7fYsXav1IpQdmhHP/z6vbUHBjfgljkKGaigsr
2wff8u0Q/1G4zCWQzBjixMkjU.....I22.........UaNalD.A....6E3.G.....................
.............oAnAt1...sD....zIg7..................................kmEwMEw....k1.
.....4iSoz1.....eyTl.QLMyVUc.g8.G....Y0....9....x2...k3...E9....//...k1z....SX5g
...U.a0KyRLs4rPMRYoWyx7lz16.0c..0nBr...........U6.cXcESLfz1...........228.UEkw..
.Ub96aAIVz9.1se7Umvxz8...........RU0.E190............s/........./.........E.0c..
zzzz.............0...................2U.8.kzzzD............8....................
/6U0.wzzz1....................................RpR1UvNPcvxDUCuc1.ibhVibw/ELRr.sSq
4uyZc.RpR1UTbfvtXl0.aJ5.yRiibb0AELRr.srtuSiLJ/RpR1.Aqthr7YpB.I5.kMbrS98LELRr..XR
Svhev/RpR1Emrrrx..EsUa3feeWCNqGQIJ36wk8EwyLsUa3f.YaQmJrQTBrOtx3QVtqPm3KPVtWOkR4.
E....2..F2E.....I....A....UG7FpL3poL4l4NTB3RVt4NV75R0J5PW/.P.w4Rn...............
..............................zD........2.2.....................................
................................................................................
........................}
{Titel: A_fld_hybrid_standartBulb}



3. 
The Saturns. Adding some background picture is advisable:

Mandelbulb3Dv18{
g.....S....O/...w....26...kq5CEErXjzz4QiBqcW390EmB9GER0oUzfFCCbfJYAszKpalGphUmyD
................................tE9mqtvbqz1.......BR./..................y.2...wD
...Uz6....Eb1....w.0/.....Ei1...e.....Ef.....2QATf0I1bqD/w......PKJ/0dkpXm1.wGr2
y.UaNadD12../..........wz.................................U0.....y1...sD...../..
.zHnAnoDgVvSxRXYdxXJv7NoguY9zGFKwhlq0EnDmYQ6SEXPgvXb26ijn7FNzY9Qr0AjYqpDdomn0sS3
twPmgoZZtOKLzuPxileMgHqDV.....IC6...r7........sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................3....k1.
.....4iSoz1.....E.kz.wzzzH.U..6.P....61...EB....X/...c3....F....6/...In4...UTH5Y
...U.4gdLzzuverz.1Akz9/../6.3c..zjyj..koWHC0esxj6MZq/OpVuz1...........k.8.UGoM0.
.MdMN9PJKz1.dHh18A7uz8........../EU0.wzzz1...........s/........./.........E.2c..
zzzz.................................2./8.kzzzD............8....................
/EU0.wzzz1...................................UArX/kOndoQUmkthn9.PrBnRro5Z8xJ.EqQ
8BbCgczGa/EUIdJUGuHdGT3.ALRjJP4Iu1nN.26JV3clQJeoL/.NndoQS.rthn9.7nAgAXQSFCeQ.UpN
1RqzzVArX/kOndoQ...mQDKmZgWy9NaUEtHdGTphf.ZykQqQ.cLEgRKNW7LMdBqQi.ZH5/.Ai.bPb/kL
E....2..F2E.....I....M....UG7FpL3poL4l4NTBJMoJbQi/..............................
...............................EbNaNaNaNoz1.....................................
................................................................................
........................}
{Titel: saturn_apple3_fst}




4. 
Deep zoom into first FLD formula:

Mandelbulb3Dv18{
g.....N....m....w....EE...EdpA4zRmEmzo7OTJbiZ./EGS38NwYVMzvqHD/iD5Y/.Rv87GaZA7xD
................................uqFfK3Eg2/2........5./.........E........y.2...wD
...Uz6/..........EU0/.....ks/...q.....E4.....YOup3Qma1mD/.kmEwME...m/xa21g1....U
z.....cD12../.Uo5zfqrOogzOAshklLzL.EJbULK34c3z1...........U0.....y1...sD...../..
.wXaNadDIp50d80f.wvDukeacdwtyuomi.K1PJijPZZKMEhhGv1oupVEWh3wyQg9UGCVe/kjAOuqGNRY
ivn1etyQ2IjzyGWu3eQHxdijU.....IU0.........UaNalD.A....6E0.G.0...................
.............oAnAt1...sD....zIg7................3P0...............kmEwME6....k1.
.....4iSoz1.....eyTl..6E.UUc.g8.G....Y0....9....x2...k3...E9....//...k1z....SX5Y
...U.a0KyRLs4rPMRYoWyx7lz16.0c..0nBr............6............0........228.UEkw..
.Ub96aAIVz9.1se7Umvxz8...........RU0.E190............s/........./.........E.0c..
zzzz.............0...................2U.8.kzzzD............8....................
/6U0.wzzz1....................................RpR1UvNPcvGDE/Px6.ibhVi9t/ELRr.sSq
4uita.RpR1UTbfvteeG/Px6.yRiibXf9ELRr.srtuSS6F/RpR1.AqthrIJJ/Px6.kMbrSnFKELRr..XR
SvBkz/RpR1UvNPcv..EsUa3feeWCNqGQIJ36wk8EwyLsUa3f.YaQmJrQTBrOtx3QVtqPm3KPVtWOkR4.
E....2..F2E.....I....A....UG7FpL3poL4l4NTpYMmx4RFp2B2/..spYMmx4Rn...............
..............................zD..........2.....................................
................................................................................
........................}
{Titel: A_Afold_Totestall}




5. 
Simple hybrid of BoxBulb and Folded Newton Triplets power 3 showing charasteric features of both, p=4 shape of squircle / superelipse of BoxBulb and drum like shapes of Newton triples:

Mandelbulb3Dv18{
g....UA....Y/...w.....A...ExX3X3tD62.LtxCSw3buxjCo7NpJDQixXeJqCJuIrlzmOnVGQ7K/.k
................................9cTR.mvK/.2........A./.........E........y.2...wD
...Uz6/..........6.0/......f/...c.....E......YD7IwRaZErD/..........m/dkpXm1....k
y.....cD12../.UEb6q4lPwczG/nvMMETJ.kfzIKB6a9..A...........U0.....y1...sD...../..
.wXaNadDoUQ8PI/QXxnuUpRKoar.zyj3GWM4cIojbrimb.oVnw9J9Jbk0NJMzELyjBumjDpjOpalE7in
0x1YAOnd6F6Jzwp3XCgbk0qDU..../2q0.............kD.2....sD..G.0...................
.............oAnAt1...sD....zIg7........................................3....k1.
.....4iSoz1.....k.kz.wzzz1.U..6......61....8....N....c3...kF....6/...YJB..EJcF52
...U.avrazDjTCszIxMuzjPe20..1c..enTg............6wyBIC4OWz1...........Y/8..1fk1.
.wUmc2beYz1.dA8E5Exwz0........../6X0.EG7f...mIqp.taszs/pMnDnNqyj.gM3ZaYq1zP.mc..
.Rn9..UAZRBEi7.E.0cXcESLfz1..........2U.8.kzzzD............8....................
/6U0.wzzz1...................................k1X2/UBblnNXc/kHB3.yxnDyJ.FjjDX.EsW
xg6wcd0ZI.EElRHQpx4U.06..06U.OeTwk6F.MnNwQawyl1X2/UBblnNax5DAG2.qQ4DbtuTXoM2.MnN
wQaxzl1X2/UBblnN...DAG2PiZ/kHB3RNEovvnsu4X4U.06U................................
E....6E.F2E.....I....E....UG7FpL3poL4l4NT7oPs7IRg74.............................
..............................zD........6.2.......././..........................
................................................................................
.....................2.....3....1....cIGIxJFBxZFgFqLCJqRoxaPI7LOn...............
........................................kz1........../..........................
................................................................................
................................}
{Titel: ball_unique}



6. 
Gilgamesh Head. DE based Mandelbulb3d did not want to generate it. As this was my first 3D fractal formula so I spent more time implementing it until I succeeded in tricking DE;) No julias or hybrids throught.


Mandelbulb3Dv18{
g.....S....O/...w....26...Ee01cW42Yzzm/r7576Ei.E8YJzWcYnmzvg6ULwFtbcz0AH5ktxX1.E
........................................kz1........B./..................y.2...wD
...Uz6....UP0....M.0/.....k4/...V.....E9.....omEQgisq6rD/..........m/dkpXm1.BnAH
y.EnAngD12../..........wz.................................U0.....y1...sD...../..
.zHnAnoDB5UWo9MejxH.stFbtax6zYYKFAT2t5qDZE4za.8jdw97cPa2c6XQzM3FFCgOJGkDvA89EZNw
VxvBhZyqSiG6zevswh3IjyqDU.....2n/........2....sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................w....k1.
.....4iSoz1.....6yzz.wzzz1.U..6.P....61...EB....m....k3....F....8/...I1.....SH52
...U.WeeryDfp3nz....z1....6./c..zrhe..UoK/nl2xvj6sM93P58izH...........Y/8.EM7Z2.
.wUmc2beYz1.dA8E5Exwz0........../6U0.wzzz1...........s/...................E.0c..
zzzz.............0...................2U.8.kzzzD............8....................
/6U0.wzzz1...................................QQef1EXl/9gslE60jC.tt7eceP3dlBr..bc
l4PUSYTyT0Egl0LgjjGyVj7.cmNSci0Crj7W.29Tk3vj3ZqjQ1ESQW8eYQJytz7.cWOScGYPt5ya.U8b
tVO.rRza60.e0a5e..krS7YUzzFW1tROyzXEwyxaxzprT9Yn................................
E....2..F2E.....I.........UG7FpL3poLJxpFdlqNVpKNnVINVF4.........................
...................6./........zj................................................
................................................................................
........................}
{Titel: GilgameshHead_xmr}



7. 
Zoom of hybrid of FLDs. In Navigator check "Far plane". On all movement image will disapear until "Far plane" will be re-increased. Spine lenght depends on bailout.


Mandelbulb3Dv18{
g.....c....U/...w....26....h7zh2IM1ozs7pPiiD3gzD7y9kkvPafzPLacKNDK9/.Vfuv3FNeWxD
................................kzI2rIzEw.2........7./.........E........y.2...wD
...Uz6/...Ud1....E.0/....2.z/...k....2E5.....kI6mQaQivlD/.....6EtZ410xa21i1.....
zIUaNadD12../.............................................U0.....y1...sD...../..
.wHnAnoDZ8xeUwG8MwPZ4t7i.hm5zo/mPhVxWUkD0Kw8y5qsnvfPjJ9oaxf/zcLe2oG9eCmj05/pSCeV
Uw9yErc8Kv54zaTdJEVQyQijU.....Iq4.........UaNalD.A....sD/.G.....................
.............oAnAt1...sD....zIg7......................................GE6....k1.
.....4iSoz1.......kz.wzzzbUc.g8.e....61....9....m....k3...EF....5/...M14....S15g
...U.WeeryDfp3nz3ivmz9Pdf.6.0c..0nBr...........U6.cXcESLfz1...........228.UEkw..
.Ub96aAIVz9.1se7Umvxz8...........RU0.E190............s/........./.........E.0c..
zzzz.............0...................2U.8.kzzzD............8....................
/6U0.wzzz1...................................QQef1EXl/9gslE60jC.tt7eceP3dlBr..bc
l4PUSYTyT0Egl0LgjjGyVj7.cmNSci0Crj7W.29Tk3vj3ZqjQ1ESQW8eYQJytz7.cWOScGYPt5ya.U8b
tVO.rRza60.e0a5e..krS7YUzzFW1tROyzXEwyxaxzprT9Yn.YaQmJrQTBrOtx3QVtqPm3KPVtWOkR4.
E....6E.F2E.....I....M....UG7FpL3poL4l4NTpYMmx4RFp4B2/.PW/.P....................
..............................zD..........2.....................................
................................................................................
.....................2.....3....4....cIGIxJFBxZFgFqLlJLMopYMmx4Rn.URZ/UQjFrA....
........................................kz1........../..........................
................................................................................
................................}
{Titel: Fld_Goodplace_Trilobites}







//=========================================================================================
Examples of version 1.2 formulas:


8. 
Letters made of hybridised Chudobox and Domofractal:

Mandelbulb3Dv18{
g....Es....m....w....26...UAa2UEyNe0.ryrPUNp3CAEDTSHCOCTVzXJpR/vCUDuzqjJnVUfKduj
........................................kz1....UiNcY//..................y.2...wD
...Uz6...........Q.0/....2.u....K0...2E4.....oUfaWhjhBqD/..........m/dkpXm1....U
z.UaNadD1A../2UCl2EtuRSyz.XvnLZ6zuvD05NRnKeWnz1...........U0.....y1...sD...../..
.z1...kDYevqCfnoUxXfY5Lk0VPHz8CdSBd28Yojn2U7enYPHxX8smGRmnPKzYi/m7xGhKpD39tpgz8K
6u1MWCRUNVEKz8denvfEsqpDU.....Y4a........2....sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................D....k1.
.....4iSoz1.....5.kz.wzzz1.U..6.P....61...EB....3/...c3...ED....4/...A2w...UUH5A
...U.ydelyjeYFnz....z1....6.0c..6XAm..EizccZWGyD6EdGkxmWcz1...........Y.8.EBzA0.
.sM93P58iz9.MmnWK2zwz0........../6U0.wzzz1...........s/...................E.0c..
zzzz.............0...................2U.8.kzzzD............8....................
/6U0.wzzz1...................................ozz61U7bck7RD.zzH7.aQW0b2X3mHOs.UZ2
6VJBsczNc.EJcIFJOHpzO04.JlG3JV3P..Dw.IFJJJJbm/.wk1E3JJJJOxLzzXA.aQW0bgvTxzDm.Mm7
8QW..qzz61U7bck7...zzHdwuMVwY4ikvPYybV0XJt4.k1De................................
E....6E.F2E.....I....U....UG7FpL3poLCxpEcJ5Nj7oPs/..............................
..........UaNaNaNaNmz........Y2E...........GVf53iSIxzMaNaNaNaNzDOaNaNaNaVz1.....
...0.dkpX0LD8QyD................................................................
.....................2.....3....C....cIGIxJFBxZHTFoPhxaNm3qMo34P................
...........................................iSIsuFVfjz.........zD................
...wz0........zD...................oz........U.E........Uz1........wz.........zD
........Uz1.....................}
{Titel: Chudo_Domo_Hybrid}



9. 
Weird Alladin's lamp like object made of burning ships:

Mandelbulb3Dv18{
g....ET....K0...w....26...U3z7F81//0.TjN6hcwJL0E.MQTxHhTNz9AiTrtb83pzi4XZ9SlYzzD
........................................kz1........6./..................y.2...wD
...Uz6.....D.....M.0/.....k50...z.....E3.....M8bjMjLw3rD/..........w.dkpXm1/...U
z.UaNadD12../..jjO8heFByz4m2SUPy02vDLXRq4Ubjdz1...........U0.....y1...sD...../..
.zXaNadDEh/iov3Tlx1..........4k3ipU3amdj8t1rpZuGIuHFt8qkou8OzwHewf3L4XqDezdPqW2C
IunNm0FLQNAOza/fE3AhiWqDU.....2k1........2....sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................I....k1.
.....4iSoz1.......kz.QLMy/.U..6.P....Y0...EB....x2...k3...kD....4/...I1...ULSJ52
Og3U.a0KyRLs4rPMRYoWyx7lz16.0c..0nBr...........U6.cXcESLfz1...........228.UEkw..
.Ub96aAIVz9.1se7Umvxz0...........RU0.E190............s/........./.........E.2c..
zzzz.............0...................2./8.kzzzD............8....................
/EU0.wzzz1....................................RpR1UvNPcvxDUCuc1.ibhVibw/ELRr.sSq
4uyZc.RpR1UTbfvtXl0.aJ5.yRiibb0AELRr.srtuSiLJ/RpR1.Aqthr7YpB.I5.kMbrS98LELRr..XR
Svhev/RpR1Emrrrx..EsUa3feeWCNqGQIJp2pk4EwyLsUa3f................................
E....2..F2E.....I....I....UG7FpL3poL4l2FhBLNoxZHV7LOY3aQ..EMmZ4.................
...................wz................................/........zD........kz1.....
................................................................................
........................}
{Titel: FLD_Weird_BurningShip}



10. 
Rock with mandelbrot and tricorn crystals in inside:

 Mandelbulb3Dv18{
g....6M...Uk/...w....26...UTlZjxq7i2.rlWSy5XHE0EQpRbqRBcOz9BzK6Vyw4xz4FGdKifbYwD
........................................kz1......U2W./.................U//2...wD
...Uz6....U31....w.0/.....U94...L/....Ej.....Ykgsz4OaOrD/w......7t8X/dkpXm1/aNat
x.EnAnQD12../..........wz.................................U0.....y1...sD...../..
.zHnAnQDggY2iVadqx1..........ORqRVY1C8ej47cRHuTsMunZpIGwArAQzsYHD3orTtqDUy4cg5/W
PuXsLixETzZPz4GKwyCnB1rDU.....YI7...WP........sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................W....k1.
.....4iSoz1.......kzdbzxtHUW.k6.P....61...EB....m..06c3..UUD....3/...In4..UE9L52
PQ3U.ydelajeYFnxUrPst1SjV16.2c..29Qn..EizccZWGyD6EdGkxmWcz1...........k.8.kFw61.
.sM93P58izv.MmnWK2zwzC........../6U0.wzzz1...........s/...................E.0c..
zzzz.................................2U.8.kzzzD............8....................
/6U0.wzzz1...................................cTxO1ERg7W7n5GDA2..pla6a.8Bzjim.I5P
WMGU8RY3/.ERg7W7J54oEb..pla6aUXOzzPJ.I5PWkU0zdTxO1ERg7W7QxbypfB.pla6acvTuLjq.I5P
WMmuzdTxO1ERg7W7..kzAz9xDPGD/Ml47ZnzAzPw5tH0wOA5.cZEm3qQg3aR1t0QiR4..Q2.........
E....2..F2E.....I....I....UG7FpL3poL4l2Fh7aQjFrLM3KPV7LO.oKMmZ4.................
...................wz.....................2........../........zD................
................................................................................
........................}
{Titel: zzFLD_WayOf3dMandelbrot_hardrender}







//=========================================================================================

Chudobox FoldZ=0 used like Amazing Surface. 
These parameters will work only with formula version 1.2 or later. 



11. 
In this formula sphere is (Lp space p=1) square with edges along axis hence technological looks or pyramids:

Mandelbulb3Dv18{
g.....S....O/...9....26...kmta.fmAF/.nqP7kY40ezDQhEacAhSayPFj4LdVttwzOK04EsFi7zD
................................35iJplMukz1......kIr./.........E........y.2...wD
...Uz6/...UW.....w.0/......r....i/...2E0.....k2V9FoKv2rD/wkqS9kD...m/dkpXm1.xyzT
zIEnAnYD16../2kMmUQMqNXuzAQsuXKtPayjGAyET8sL2z9...........U0.....y1...sD...../..
.w1...kDERq2TVwe2y19kAK/49C9z.B847/dbCmjELvYCS6v3w9Hdj.FIP3TzkIjKQLjSsrDUWr2tEAE
lwHghvViahVTziTtrpSEJlrDU..../Yb6...9K...2....kD.2....sD3.G.....................
.............oAnAt1...sD....zIg7..................................Uwe1vD9....k1.
.....4iSoz1.......kz.wzzz1.U..6.P....61...EB....Z0...w.....F....8/...I1.....SF52
...U.0aZczDM6/nzMg2czX6dE16./c..zrhe..UoK/nl2xvj6sM93P58iz1...........U/8.EM7Z2.
.wUmc2beYz1.dA8E5Exwz0........../6U0.wzzz1...........s/...................E.0c..
zzzz.............0...................2U.8.kzzzD............8....................
/6U0.wzzz1...................................6W6W..KMV3KJ7mzfr9.UPQWU53FW6W6.U3K
MVJPVNita1.KMV3K79LTlhB.aZpiveeTW6W6.U3KMVJwy7W6W..KMV3KRxb6W60.MV3KMhvTW6W6.U3K
MVpzz7W6W..KMV3K...KMV3Kzz/s4bslyz1KMV3KxzJWJiwZ................................
E....2..F2E.....I....U....UG7FpL3poLCxpEcJ5Nj7oPs/..............................
.............................Y3E........kzXaNaNaNaNwz..........E................
...wz...........................................................................
........................}
{Titel: Pyramids2}



12.
TMy favored parameter. These pyramids are unstable. I took a while to get rid of the noise without render takeing an eternity. The noise solidified into sandstone. Here Fisheye transformation plays some unknown role:


Mandelbulb3Dv18{
g.....U....U/...c....2I...U.iIafwo00.X8kGmpwIV.EKYUwRpeqZyvynxuKJ8FPzu65L5KVEWyD
................................afDKJ0Otkz1.....q/9Y//.........E.......U1/2...wD
...Uz6/..........wU2/......11...92....Ee.....csHxXJNf.rD/.k4UGmD....0dkpXm1.nAnA
yIEsuFdD1A../2UGQ7euqrmuzepwnu5NoeyD7GNGb2Vnny9...........U0.....y1...sD...../..
.w1...oDNACKj6TWxxHPAnoudK3AzsJ4XYalQZmjD0xmwfGKzv9.ldAxr82RzwUVPdVe6KrDjNo.KIVZ
ow17Nzd0C8MRzejH5zxpyErDU..../IMrA.......2....kD.2....sD..G.....................
.............oAnAt1...sD....zIg7..................................UpEW/Ed....k1.
.....4iSoz1.......Ei.wzzz5.U..6.Z....61...EB....m....k3....F....6/...c46....Sn5A
...U.WeeryDfp3nz3ivmz9Pdf.6.5c..zfjp..UhV8JTUGyD6.bgyNvSczH...........k/8.kdBrA.
..KCQAiZ/.A.XwE7eDZzz0........../FU0.wzzz1...........s/...........6.......E.2c..
zzzz............k....................2./8.kzzzD............8....................
/EU0.wzzz1...................................QQef1EXl/f7slE60jC.tt7eacP3dlBr..bc
lOGUSYTyT0Egl0b7jjGyVj7.cmNSag0Crj7W.29TkNmj3ZqjQ1ESQWe7YQJytz7.cWOSaEYPt5ya.U8b
tNG.rRza60.e0ab7..krS7IJzzFW1tRJyzXEwyRJxzprT9IJ.crMZ7rOjNb98/pF...I5/..........
E....2..F2E.....I....U....UG7FpL3poLCxpEcJ5Nj7oPs/..............................
.............................s1E........kzXaNaNaNaNyzcNaNaNaN4yD................
...wz...........................................................................
........................}
{Titel: Pyramids_land_zsecondrender}




//=========================================================================================
Examples of version 1.3 formulas:


Kalezobox examples


13. 
Kalezobox with sphere inversion Radius = 1.175

Mandelbulb3Dv18{
g.....c....s/...S....26...UEIUBxgIN0.DwNxdug8./EvOEyXrV7JwXCRKdIPCGxzmTsLhr/FbyD
................................FLlv0qkyjz1........6./..................2/2...wD
...Uz6....UiB....Q.0/....2EM....1/....E9.....Ur/XjZXKhqD/Q......BJJ/0dkpXm1....U
z.UaNadD12../..........wz................................AU0.....y1...sD...../..
.zHnAnoDT8zZNtcJfx1..........m9OgNtBZNdjnjDFb79EAu1yFg.KdOHNzYYyE8CTy2qDK3Ji0lAM
FuHg8B.twtHMzSqU1NJeqIqDU.....2C5...FB...2....sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................6....k1.
.....4iSoz1.......Er.QLMy/U6.UC.f....Y0...k6....x2...c3...E9....j....cK2....TN5A
...U.a0KyRLs4rPMRYoWyx7lz1..0c..rTzx...MarH7iXyD6oa4dabdnz1...........I.8.UF4N2.
.sM93P58iz9.eLISw7kxz0........../6U0.wzzz1...........s/........./.........E.0c..
zzzz............N1...................2U.8.kzzzD............8....................
/6U0.wzzz1....................................RpR1UvNPcvxDUCuc1.ibhVibw/ELRr.sSq
4uyZc.RpR1UTbfvtXl0.aJ5.yRiibb0AELRr.srtuSiLJ/RpR1.Aqthr7YpB.I5.kMbrS98LELRr..XR
Svhev/RpR1Emrrrx..EsUa3feeWCNqGQIJ36wk8EwyLsUa3f................................
E....2..F2E.....I....c....UG7FpL3poLCxpGVlKNuxaEjV5.............................
...................wz.........zDOaNaNaNadzHnAnAnAngwz...................6.2.....
...../.........E..........2.....................................................
........................}
{Titel: Kalezobox_sphInv1p175}




14.
General look on Kalezobox with 4,4,4 Lp space Curvature and julia like added value:

Mandelbulb3Dv18{
g....kf....j0...w....26...kc4AvgOVT5.zw2MXZOnN.EMNqBrmjjZznEvuh94mUvz25VSsrrfFyD
................................XIXgOVVoVz1........A./.........E........./2...wD
...Uz6/...kGF....w.0/.....kB0...2/....E9.....owWYGWShNrD/w.........G0dkpXm1.....
./UaNaVD12../.............................................U0.....y1...sD...../..
.w1...kDiggXlijv0yHMEr10PVj6zi5M4rOZPGqjWDpBSnM/HxPIxMnLRACUzAsVM.UMfBrjUJfr4STI
WxnQsvdn2kzQzYqj02Ml//sDU..../YEF...vU...2....kD.2....sD..G.....................
.............oAnAt1...sD....zIg7........................................K....k1.
.....4iSoz1.......kz.wzzzL.U..6.5....61...EB....m....c3...k7....8/...I1....Sw752
.....wdelyjeYFnz....z1....6.5c..zfjp..UhV8JTUGyD6.bgyNvScz1...........k/8.kdBrA.
..KCQAiZ/.A.XwE7eDZzz8........../RU0.E190............s/........./.........E.lc..
zzzz.............0........E..........2U.8.kzzzD............8....................
/6U0.wzzz1...................................ozz61U7bck7RD.zzH7.aQW0b2X3mHOs.UZ2
6Vp0swRQe/EJcIFJOHJyRO4.JlG3JV3P..Dw.IFJJJJbm/.wk1E3JJJJOxLzzXA.aQW0bgvTxzDm.Mm7
8QW..qzz61U7bck7...zzHdwuMVwY4ikvPYybV0XJt4.k1De................................
E....2..F2E.....I....c....UG7FpL3poLCxpGVlKNuxaEjV5.............................
...................wz.........zD........kz1........wzMaNaNaNaNxD........2.2.....
...2./......../E........E.oAnAnAnAnoz0..........................................
........................}
{Titel: Kalezobox_sC444vAdd03}



Elazobulb examples:

15.
Mandelbulb with powers 4 and -4 - so lots of holes /// sCurvature of 2, 2, 3 - flat bottom without crater in poles, longer arms and hourglasses in inside.


Mandelbulb3Dv18{
g....ET....x/...m....26...EB4sS.Kvb0.nmlSTy6tVzDNCDBHyrtYznf08ReszqxzuT4XYihVCzD
................................t2.2We1vjz1........4./..................y.2...wD
...Uz6...........w.0/.....UP/...x.....E5......EboVpA54rD/.........Uy/dkpXm1.BnAH
y.EnAngD16../..........wz.................................U0.....y1...sD...../..
.zHnAnoDGpzRbNCg1yPLPa6PsQnQzGVUUU7nNQkjuXrOfli/bx1PKZPOODoRziErk08xa4sjoIkXCHKl
ix16pB95cOwTz8c6ZEU5pbrDU.....o28........2....sD.6....sD..G.....................
.............oAnAt1...sD....zIg7........................................w....k1.
.....4iSoz1.......Ei.wzzz5.U..6.Z....61...EB....m....k3...UE....7/...MHB....SL5A
Wc3U.WeeryDfp3nz....z1....6.5c..zfjp..UhV8JTUGyD6.bgyNvSczH...........k/8.kdBrA.
..KCQAiZ/.A.XwE7eDZzz0........../FU0.wzzz1...........s/...........6.......E.2c..
zzzz............11...................2./8.kzzzD............8....................
/EU0.wzzz1...................................QQef1EXl/f7slE60jC.tt7eacP3dlBr..bc
lOGUSYTyT0Egl0b7jjGyVj7.cmNSag0Crj7W.29TkNmj3ZqjQ1ESQWe7YQJytz7.cWOSaEYPt5ya.U8b
tNG.rRza60.e0ab7..krS7IJzzFW1tRJyzXEwyRJxzprT9IJ.c5HVlKOnVa98/pF................
E....2..F2E.....I....M....UG7FpL3poLCxJFg3aSj7IRg74.............................
...................2./......../k........Uz1........../.........E........6.2.....
................................................................................
........................}
{Titel: Elazobulb_hands}



16.
Parameter with space curvatures 1, 2, 5. Here 1 - introduces slightly stretched angular "leaf" shapes. And the empty spaces thanks to Formula 2 power = -2.5.

Mandelbulb3Dv18{
g.....c....s/...S....26...EGGX/dnrF0.The/Q6t1AyDpHk1WJ08dyX7ix4wdU7rzShe/Q6t1AyD
........................................kz1........6./..................y.2...wD
...Uz6...........s.0/.....ER....X....2E5.....AANe04JGhqD/.EnAnoDnee70dkpXm1.BnAH
zIUaNadD16../2.........wz...................Ez9..........2U0.....y1...sD...../..
.zHnAnoDZGCsp4vSlx1y8hs/3/S1zsIL37ckkXkD1/MJfO4NHwPQJ9xr0g7PzIBTmmWuPEqDn/YF8JJl
NvfVr72TRn/Nzae33GNyPmqDU.....Yr6........2....sD.6....sD..G.....................
.............oAnAt1...sD....zIg7..................................kAnAvDS....k1.
.....4iSoz1.......El..Yhz4ES..E.Z....61...EN....m....k3....F....6/...cKB....SP52
...U.Weer02fp3XhYHSGz8Pdf.6.5c..zfjp..UhV8JTUGyD6.bgyNvSczH...........k/8.kdBrA.
..KCQAiZ/.A.XwE7eDZzz0........../FU0.wzzz1...........s/...........6.......E.2c..
zzzz............k....................2./8.kzzzD............8....................
/EU0.wzzz1...................................QQef1EXl/f7slE60jC.tt7eacP3dlBr..bc
lOGUSYTyT0Egl0b7jjGyVj7.cmNSag0Crj7W.29TkNmj3ZqjQ1ESQWe7YQJytz7.cWOSaEYPt5ya.U8b
tNG.rRza60.e0ab7..krS7IJzzFW1tRJyzXEwyRJxzprT9IJ.cbSnJ5QZ7bPjNLMT3X98/pF........
E....2..F2E.....I....M....UG7FpL3poLCxJFg3aSj7IRg74.............................
...................5./.......E.k........Uz1........wz..........E........I.2.....
................................................................................
........................}
{Titel: Superseed_lotus2}








  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *

7. Mathematics
About some of the things used.



Lp spaces
Number of these formulas uses Lp spaces. Boxbulb is IQ bulb in p=4 space, FLD Boxbulb (p=4), Transf_Fisheye8 (p=8 space), Techna_transform (p=1), Elazobulb, Kalezobox and Chudobox (p=1) were it was used only for speed.

https://en.wikipedia.org/wiki/Lp_space

I don't understand mutch of that article but "An analogy to this is by taxi drivers who in a grid street plan should measure distance not in terms of the length of the straight line to their destination." hence p=1 norm is called taxicab distance.
 
In practice radius is calculated  by R= p power root of (|x|^p+|y|^p+|z|^p) so:
p = 1 is "diamond", (square standing on the edge), 
p = 2 is everyday circular radius, 
p = 4 is "advanced" streamlined square favored by cell phone designers: 

https://en.wikipedia.org/wiki/squircle

Alsou inter-city tourist buses are p=4 or p=3 shapes. They are:

https://en.wikipedia.org/wiki/superelipse



Forum replay on Lp spaces
CozyG « Reply #3 on: July 30, 2017, 07:47:15 PM »
"The easiest way to understand p-norms (at least for me) is to consider them as different ways to measure distance. For p=2 (the 2-norm), in 2D you get distance = sqrt(x^2 + y^2), which is the Euclidean distance we consider the normal way to measure distance in 2D space. But consider the 1-norm (when p=1): distance = abs(x) + abs(y). The 1-norm is also called the taxicab distance, in reference to a taxicab travelling along an idealized grid of streets. In a taxicab, the important measure (for both driver and passenger) is not the Euclidean distance from point A to point B "as the crow flies", but the taxicab distance which will be the sum of the distances along each street. So p-norms are different but potentially valid ways of measuring distance."





Superseed
Inspired by superformula I made different curvatures of p in each axis. Analogy could be Flat Earth with direction "up" being very different from directions "north" or "east".

Mean power of 3 p-s (sCurvatures) is calculated by geometric mean, and then inverted to root:
invpower= 1/ cubic root (sCurvatureX * sCurvatureY * sCurvatureZ)


Optimised:
invpower:=power(PowerX *PowerY *PowerZ*PowerW,-0.33333333333333333333);
(It needs a lot of 3s, this is visible. Numbers of 3s depends on Double or Float)

Then radius is calculated by
R= (abs(x)^sCurvatureX + abs(y)^sCurvatureY + abs(z)^sCurvatureZ)^invpower;

What I got I called a superseed becouse some combinations looks like seeds. 
Then it is visialised by iterating radius in modified sigma function:

divisor:= 1/(Sigma+1);
temp:= (Sigma + R )*divisor;
(x,y,z) := temp*(x,y,z)
 






Fisheye or sigma function
Flame fractals have transformations Fisheye and Eyefish. In Apophysis:

radius = square root of( x^2 + y^2)
temp = 2/(r+1)
(x,y) = temp*(x,y)

It generates scenery as fish eye lens but mathematicaly it is sigma function applied to radius:
https://en.wikipedia.org/wiki/sigma_function



Here Fish eye transformation is like follows:

temp:= (Sigma + R )/(Sigma+1);
(x,y,z) = temp*(x,y,z)


It keeps values slightly to 1 but allows them to rise.
Sigma in different formulas is "Strenght", "antiFisheye" or "strangeness". The larger the value the less the effect. Until it reaches -1  what is division by zero, then larger negative values creates larger inversed spheres.






Interpolation
Here I used interpolation between 0 (first thing) and 1 (second thing)

modulus:=1- Strenght_Interpol;
(x,y,z) = (x1,y1,z1)*Strenght_Interpol + (x,y,z)*modulus;


It is like points on 0 and 1 on ruler. 0.5 is middle but negative values or values > 1 is extrapolation. I used this becouse it takes just one number instead of two "weights".






Spherefold
Tglads spherefold of Amazingbox/mandelbox is like this:

r2 := x_tmp*x_tmp + y_tmp*y_tmp + z_tmp*z_tmp;
rmin2 := Rmin*Rmin;
  if r2 < rmin2 then
    begin
      temp := 1/rmin2;
    end
  else if r2<1 then
    begin
      temp := 1/r2;
    end
  else
    begin
      temp := 1;
    end;

(x,y,z)=(x,y,z)*temp

It actualy does two things. One is fold around sphere and another is sphere inversion with radius 1. Here Chudobox uses fold around sphere and Kalezobox uses sphere inversion between a radius and min radius. 
Sphere inversion by changable radius is:

temp := scale*Radius_SI*Radius_SI/(radius*radius);






Boxfold
It orginaly was writen with conditionals:
if component > 1:
 component := 2 - component
else if component < -1:
 component := -2 - component

Hovewer in Mandelbulb3D most of Amazingbox/Mandelbox formulas uses algebraic formula:
x := abs(x+Fold) - abs(x-Fold) - x;
y := abs(y+Fold) - abs(y-Fold) - y;
z := abs(z+Fold) - abs(z-Fold) - z;


In all formulas I used:
x := x +  abs(x- FoldX) - abs(x+ FoldX)  ; 
y := y +  abs(y- FoldY) - abs(y+ FoldY)  ;
z := z +  abs(z- FoldZ) - abs(z+ FoldZ)  ;

I had forgoten why I used this modified version. In many formulas these are identical. However not in Amazingbox/Mandelbox. But who needs another slightly different Abox. 
Rectangular folding with changable x and y and z folds have number of advantages. Then gabarites of fractal can be adjusted and if one of those folds =0 then it is like Amazing surface formula.





Unit vector addition
This is what does _asdamTrans. Unit Vector is vector of same orientation but of the lenght of 1. 
Unit vector = x,y,z / |x,y,z| 

https://en.wikipedia.org/wiki/Unit_vector

Adding unit vector multiplied by some small value (0.2) to the base vector will shrink the fractal. (It escapes sooner) However adding it multiplied by some negative value enlarges the fractal. Result looks just like adding more or less air to the balloon.

Hence in Domofractal unit vector is substracted by Thickness value.
radius :=sqrt(x*x+y*y+z*z) ;
x:= x - Thickness*x/radius ;
y:= y - Thickness*y/radius ;
z:= z - Thickness*z/radius ;





Conj function of Y
Quaternion conj is all imagineries of oposite sign conj(x,y,z,w) = (x,-y,-z,-w). Pretty simple.
Hypercomplex number squareing does not generate very interesting mandelbrot fractal
x1:= x*x - y*y - z*z + w*w;
y1:= 2*x*y - 2* z*w;
z1:= 2*x*z - 2* y*w;
w1:= 2*x*w + 2* y*z;

With conj function of just Y conj(x,y,z,w) = (x,-y,z,w) hypercomplex squaring becomes:
x1:= x*x - y*y - z*z + w*w;
y1:= 2*z*w - 2* x*y;
z1:= 2*x*z - 2* y*w;
w1:= 2*x*w + 2* y*z;

Which is nice 3D tricorn fractal just like one generated by Tricorn.3mf mandelbulb. (But there the z is negative.)

Maybe becouse in fractal generation large role is played by
https://en.wikipedia.org/wiki/Symmetry_breaking

And then it have important property of X <> Y <> Z not shared by quaternions.




Newtonian Triplets
Used in few formulas they are the visualisation of this:
https://jehovajah.wordpress.com/2012/09/13/the-newtonian-triple/

They are more interesting in FLD formulas not as plain mandelbrots. In z=z*z+c they are extruded rotated by 45 mandelbrot sets.




Scaling and descaling C
Scaling is one of the basic functions (x,y,z)=(x,y,z)*scale
However scaling interfere with other transformations. 
In FLDmset:
initialisation of (x,y,z) with pixel values
fold
scaleing
rising power
+ pixel/scale
If pixel values (C) is not divieded by scale the fractal is stretched. 

 +C/scale is used in Kalezobox. Without this fractal is more flat box without so noticable spherical parts. It should do the same in amazingbox. 




Addition
x=x+addition ; y=y+addition ; z=z+addition
It don't change mutch, but with few parameters I found that it usefull when I need to move fractal around and finetune it.
Of corse if addition values is different it is like Julia set.


