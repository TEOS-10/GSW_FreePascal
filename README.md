# GSW_FreePascal

GSW_FreePascal is a FreePascal/Lazarus wrapper for [GSW-C#master](https://github.com/TEOS-10/GSW-C/), which is the C implementation of the Thermodynamic Equation of Seawater 2010 (TEOS-10).

## Installation

This module is just a wrapper so you have to have a binary version of GSW-C installed on your machine.

There are two ways of getting it:

1). Build it yourself following [GSW-C](https://github.com/TEOS-10/GSW-C/) instructions. This way is highly recommended;

2). Use [precompiled binaries](https://github.com/kouketsu/GSWCBuilder/releases). This approach is experimental and may not work on your system.

To use the module in your code simply copy 'gibbsseawater.pas' into your project folder and add it to the 'uses' section.

```
uses GibbsSeaWater; 
```
If you work on Windows just put 'libgswteos-10.dll' next to your executable.


## Example

```
Procedure GSW_test;
Var
  sa, ct, t, p: double; //initial data
  res1, res2, res3:double; //results
Begin
  sa:=36;
  ct:=28;
  t:= 20;
  p:= 1023;
 
  res1:=gsw_adiabatic_lapse_rate_from_ct(sa, ct, p);
  res2:=gsw_c_from_sp(sp, t, p);
  res3:=gsw_cp_ice(t, p);

  writeln(res1+#9+res2+#9+res3);
End;

```

## About TEOS-10

Comprehensive info on TEOS-10 can be found on the [official site](http://www.teos-10.org) and [official repository](https://github.com/TEOS-10).
