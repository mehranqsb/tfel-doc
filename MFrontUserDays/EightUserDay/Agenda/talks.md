---
title: Agenda of the eigth `MFront` User Meeting
author: Thomas Helfer
date: 14/10/2022
toc: true
numbersections: true
lang: en-EN
geometry:
- paper=a4paper
- margin=2cm
link-citations: true
colorlinks: true
figPrefixTemplate: "$$i$$"
tabPrefixTemplate: "$$i$$"
secPrefixTemplate: "$$i$$"
eqnPrefixTemplate: "($$i$$)"
bibliography: bibliography.bib
csl: iso690-numeric-en.csl
---

# Overview of `TFEL-4.1` and `MGIS-2.1`.

- Thomas Helfer
  - CEA Cadarache, IRESNE, DES, DEC, SESC, LSC, 13 108 St Paul lez Durance, France.
- Maxence Wangermez
  - CEA Cadarache, IRESNE, DES, DEC, SESC, LSC, 13 108 St Paul lez Durance, France.

# The role of geometrically necessary dislocations flow in viscoplastic behavior of polycrystalline uranium dioxide

- Hakima Bouizem
  - CEA, DES, IRESNE, DEC, SESC, LM2C, F-13108 Saint-Paul-lez-Durance, France
  - Aix-Marseille Université, CNRS, Centrale Marseille, LMA, F-13453 Marseille Cedex 13 , France
- Étienne Castelier
  - CEA, DES, IRESNE, DEC, SESC, LM2C, F-13108 Saint-Paul-lez-Durance, France
- Vincent Taupin
  - Université de Lorraine, CNRS, Arts et Métiers, LEM3, 57070 Metz, France.
- Frédéric Lebon
  - Aix-Marseille Université, CNRS, Centrale Marseille, LMA, F-13453 Marseille Cedex 13 , France
- Jean-Marie Gatt
  - CEA, DES, IRESNE, DEC, SESC, LM2C, F-13108 Saint-Paul-lez-Durance, France

!["(left) GNDs density in deformed \(UO_{2}\) (right) Plastic flow"](img/Bouizem.png ""){#fig:bouizem width=75%}

**keywords**: Geometrically Necessary Dislocations (GNDs), Field
  Dislocation Mechanics (FDM), Viscoplasticity, Dislocation
  substructures, Fast Fourier Transform (FFT).

Polycrystalline uranium dioxide (UO$_2$) is commonly used as nuclear
fuel, in Pressurized Water Reactors (PWRs), in the form of cylindrical
pellets. At high temperatures, the viscoplastic behavior of the fuel is
controlled by the dislocation motion. Microscopic investigations on
deformed pellets [@ben_saada_sub-boundaries_2017] have highlighted the
development of dislocation substructures: the dislocations were mostly
organized in sub-boundaries, subdividing the grains into sub-grains.

The formed sub-boundaries are associated to the presence of
Geometrically Necessary Dislocations (GNDs) [@kroner_continuum_1981].
Such dislocations induce a lattice curvature in order to accommodate
local deformation produced among grains and rearrange in dislocation
walls. At the polycrystal scale, one should consider the coupling of
GNDs with Statistically Stored Dislocations (SSDs). SSDs are the
dislocations of opposite orientation that mutually cancel when brought
together, have no effect on lattice curvature, and only contribute to
the plastic flow. Classical crystal plasticity models evaluate the
deformation by the single contribution of the SSDs. To include the
crystal plasticity of GNDs, an approach based on Field Dislocation
Mechanics (FDM) theory [@acharya_model_2001], which models the
deformation due to GNDs glide on slip systems, is developed. GNDs
densities are obtained through incompatible plastic deformations between
adjacent grains with different orientations, following Kröner's equation
[kroner_continuum_1981].

First, the glide velocity of GNDs and SSDs densities is identified on
UO$_2$ single crystal tests.  
Then, the proposed model is used to simulate an imposed speed
compression test of a polycrystal of UO$_2$:

- crystal plasticity model has been developed using MFront;
- mechanical equilibrium and Kröner's equation are calculaqted by Fast
  Fourier Transform (FFT) using TMFFT solver, which is connected to
  MFront.

The test, reported on Figure @fig:bouizem, shows: accumulation of GNDs
at the grain boundaries, glide within the grains, and the formation of
sub-grains. Results predicted by the model demonstrate, qualitatively, a
good agreement with the experimentally observed dislocations
substructure in deformed UO$_2$.

# Random 3D generation of MOX nuclear fuel microstructure and mechanical homogenization

- Akram el Abdi
  - CEA, DES, IRESNE, DEC, SESC, LM2C, F-13108 Saint-Paul-lez-Durance, France
  - now at EDF R&D, MMC, F-77818 Moret-sur-Loing, France
- Étienne Castelier
  - CEA, DES, IRESNE, DEC, SESC, LM2C, F-13108 Saint-Paul-lez-Durance, France
- Rodrigue Largenton
  - EDF R&D, MMC, F-77818 Moret-sur-Loing, France
- Antoine Bouloré
  - CEA, DES, IRESNE, DEC, SESC, LSC, F-13108 Saint-Paul-lez-Durance, France
- Christian Lantuéjoul
  - Centre de Géosciences, MINES ParisTech, F-77300 Fontainebleau, France
- Jean-Claude Michel
  - Aix-Marseille Université, CNRS, Centrale Marseille, LMA, F-13453 Marseille Cedex 13 , France

!["(left) Experimental map of Pu content (right) New 3D generated microstructure"](img/ElAbdi.png ""){#fig:elabdi width=75%}

**keywords**: continuous random media, Mechanical calculation by FFT,
  Mechanical homogenization by NTFA, Model reduction

The MOX is a nuclear fuel composed of plutonium (Pu) and uranium oxides.
Its microstructure is recognized by maps of Pu content obtained by
electron microprobe (Figure @fig:elabdi left). The MOX texture is
classically approached by a three-phase particulate microstructure with
two inclusion phases dispersed in a continuous matrix.

In reality, the Pu content is continuous in space. The objective of this
work is to generate in 3D a new microstructure that takes into account
the continuity of Pu content, to check the effect of this continuity on
mechanical behavior by performing mechanical calculations, and finally
to identify a homogenized mechanical law based on the new
microstructure.

A new random model, based on a combination of random sets and functions,
was used to better characterize the microstructure, and its
characteristics are obtained after filtering the measurement noise from
the experimental map. The random model simulation gives a new
microstructure of three phases, with a variability of the Pu content in
each phase (Figure @fig:elabdi right).

From a mechanical point of view, the nuclear fuel is a material with
non-linear aging viscoelastic behavior and free swelling, which depends
on the local plutonium content. Mechanical calculations, using a FFT
method, were performed on the 3D generated microstructures, and the
results show that the effect of variability is important on the local
mechanical fields and the effective behavior.

Finally, the NTFA method, previously used for the same material, is
extended to take into account the Pu content variability, and optimized
by linearizing the non-linear behavior using the tangent second-order
approximation (NTFA-TSO). The law is implemented in the `MFront` format,
and tested by using `MTest` tool. The predictions of the new reduced
model are in good agreement with full-field simulations with a reduced
number of internal variables.

 

# References