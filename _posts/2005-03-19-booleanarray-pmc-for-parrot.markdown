---
layout: default
title: *BooleanArray PMC for Parrot
---

<p>
My Easter project is to look into the FixedBooleanArray and ResizableBooleanArray PMC. As the name implies, a *BooleanArray is an array of boolean values. This functionality could be achieved with a *PMCArray of Boolean PMCs. However this wastes a lot of memory, as a bool really just needs a single bit.
</p><p>
Currently there is a minimal implemention from Matt Fowles. The downside of the current implementation is that a bool is stored in an INTVAL. This means that 31, or 63, bits are wasted per bool.
</p><p>
Making the current implementation to use 1 bit per bool should be straightforword. But as laziness if one of my virtues, it would be nice if somebody has already done the work. My first idea was to steal the code from Perl5's Bit::Vector. This module looks very nice and very complete, with a lot of tests. Bit::Vector is XS-based and the  C-code can also be used without Perl. The downside is that the C-library is under GPL, which makes it hard to incorporate in Parrot.
</p><p>
The docs of Bit::Vector mentions that the module  is also a big integer math library. Well, a bit vector is really the same as a big integer. Thus it would be economical, if the BigInt PMC and the *BooleanArray PMC have the same implementation in Parrot
</p><p>
The BigInt PMC is implemented by calling out to GMP, the GNU Multiple Precision Arithmetic Library. When there is no GMP, than a fallback implementation jumps in. Of course, all the methods needed for *BooleanArray are already implemented in GMP.
</p><p>
So that's the plan:
</p><ol>
  <li>Steal the test suit from Bit::Vector</li>
  <li>Let *BooleanArray PMC call out to GMP</li>
  <li>Make the fallback implementation use 1 bit per bool</li>
  <li>Factor out common code of BigInt and *BooleanArray</li>
</ol>
