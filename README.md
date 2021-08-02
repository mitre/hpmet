HPMET (Human Perceptions of Machine-Edited Text) Dataset
---

This dataset is described and used in the paper "Perceptual Models of
Machine-Edited Text." ACLWEB LINK HERE. In the accompanying JSON lines
file you will find 14400 A/B test examples, each corresponding to one
human judgment.

Each of six judges judged 600 examples from arxiv and reddit
for meaning preservation and detectability. See the paper for more
information on their definitions along with the accompanying prompts.

The file is ascii json, although there are plenty of unicode
charatcers present that a good json reader will automatically convert
for you. The ascii files help readers notice the changes made by the
"viper" editor and can be useful for debugging.

The following fields are present in each object in the json lines file:

| Field Name  | Description  |
|---|---|
| judge | Identifier of the judge who made the judgment |
| set  |  "arxiv" or "reddit", source of the example |
|  task | "meaning" or "detect"  |
| packet_index  | Index of example during packet creation. Packets were shuffled after these were assigned.  |
| id  |  Reference to the sentence suitable for finding it in the internet |
| system_a  |  Identity of the machine editor responsible for edit_a |
|  system_b |  Identity of the machine editor responsible for edit_b |
| edit_a  | Output of system_a when applied to the original sentence  |
| edit_b  | Output of system_b when applied to the original sentence  |
| original  | The original sentence  |
| previous_sentence  | The sentence immediately preceeding the original sentence  |
| next_sentence  | The sentence immediately after the original sentence  |
| judgment  | "a" or "b" (or "t" for tie), the judge's selection  |
| abstract  | The complete abstract or reddit post  |
| split  | "TRAIN", "VAL", or "TEST" - which set this item was in for experiments |

Random samples from the dataset:
```json
{
  "judge": 6,
  "set": "arxiv",
  "task": "meaning",
  "packet_index": 524,
  "id": "0801.0186-1",
  "system_a": "viper",
  "system_b": "charswap",
  "edit_a": "The fr\u0430ctal dimension sati\u0455fies an equation written by th\u0117 free energy of the six-vertex model.",
  "edit_b": "The fractal dimension satisfies an equation written by the free energy of thu six-vertex model.",
  "original": "The fractal dimension satisfies an equation written by the free energy of the six-vertex model.",
  "previous_sentence": "Fractal structure of the six-vertex model is introduced with the use of the IFS (Iterated Function Systems).",
  "next_sentence": "It is pointed out that the transfer matrix method and the $n$-equivalence relation introduced in lattice theories have also been introduced in the area of fractal geometry.",
  "judgment": "b",
  "abstract": "Fractal structure of the six-vertex model is introduced with the use of the IFS (Iterated Function Systems). The fractal dimension satisfies an equation written by the free energy of the six-vertex model. It is pointed out that the transfer matrix method and the $n$-equivalence relation introduced in lattice theories have also been introduced in the area of fractal geometry. All the results can be generalized for the models suitable to the transfer matrix treatment, and hence this gives general relation between solvable lattice models and fractal geometry.",
  "split": "TEST"
}
{
  "judge": 1,
  "set": "arxiv",
  "task": "detect",
  "packet_index": 589,
  "id": "1501.05638-1",
  "system_a": "vae",
  "system_b": "scpn",
  "edit_a": "Shih ) not have no origin ) but seems not have been to ( in the classical physical part ( physical model.",
  "edit_b": "In the actual physical vacuum of free space, no one is observed in the actual physical vacuum of free space.",
  "original": "quasiparticles) that have no analogy (or have not yet been observed) in the actual physical vacuum of free space.",
  "previous_sentence": "An important and continuing theme of modern solid state physics is the realization of exotic excitations in materials (e.g.",
  "next_sentence": "Although they are not fundamental particles, such quasiparticles do constitute the most basic description of the excited states of the \"vacuum\" in which they reside.",
  "judgment": "a",
  "abstract": "An important and continuing theme of modern solid state physics is the realization of exotic excitations in materials (e.g. quasiparticles) that have no analogy (or have not yet been observed) in the actual physical vacuum of free space. Although they are not fundamental particles, such quasiparticles do constitute the most basic description of the excited states of the \"vacuum\" in which they reside. In this regard the magnetic textures of the excited states of spin ices, magnetic pyrochlore oxides with dominant Ising interactions, are proposed to be modeled as effective magnetic charge monopoles. Recent inelastic neutron scattering experiments have established the pyrochlore material Yb$_2$Ti$_2$O$_7$ (YbTO) as a quantum spin ice, where in addition to the Ising interactions there are substantial transverse terms that may induce quantum dynamics and - in principle - coherent monopole motion. Here we report a combined time domain terahertz spectroscopy (TDTS) and microwave cavity study of YbTO to probe its complex dynamic magnetic susceptibility. We find that the form of the susceptibility is consistent with monopole motion and a magnetic monopole conductivity can be defined and measured. Using the unique phase sensitive capabilities of these techniques, we observe a sign change in the reactive part of the magnetic response. In generic models of monopole motion this is only possible through introducing inertial effects, e.g. a mass dependent term, to the equations of motion. Analogous to conventional electric charge systems, measurement of the conductivity's spectral weight allows us to derive a value for the magnetic monopole mass, which we find to be approximately 1800 electron masses. Our results establish the magnetic monopoles of quantum spin ice as true coherently propagating quasiparticles of this system.",
  "split": "VAL"
}
{
  "judge": 2,
  "set": "arxiv",
  "task": "detect",
  "packet_index": 596,
  "id": "1604.03664-2",
  "system_a": "scpn",
  "system_b": "vae",
  "edit_a": "So we revisit the so-called small particle of photoelectron emission, we will provide an analytical model for the use of the photoelectric mass of small dust particles in accordance with in between at in at about",
  "edit_b": "Here we apply the well - called high energy distribution of electron water, provides an accurate bound to that electron energy to for the energy of, which is to energies.",
  "original": "Here we revisit the so-called small particle effect of photoelectron emission and provide an analytical model to estimate photoelectric quantum yields of small dust particles in sizes down to nanometers.",
  "previous_sentence": "An estimate of the photoelectric processes contains an ill-defined parameter called the photoelectric quantum yield, which is the total number of electrons ejected from a dust particle per absorbed photon.",
  "next_sentence": "We show that the small particle effect elevates the photoelectric quantum yields of nanoparticles up to by a factor of $10^3$ for carbon, water ice, and organics, and a factor of $10^2$ for silicate, silicon carbide, and iron.",
  "judgment": "b",
  "abstract": "Photoelectron emission is crucial to electric charging of dust particles around main-sequence stars and gas heating in various dusty environments. An estimate of the photoelectric processes contains an ill-defined parameter called the photoelectric quantum yield, which is the total number of electrons ejected from a dust particle per absorbed photon. Here we revisit the so-called small particle effect of photoelectron emission and provide an analytical model to estimate photoelectric quantum yields of small dust particles in sizes down to nanometers. We show that the small particle effect elevates the photoelectric quantum yields of nanoparticles up to by a factor of $10^3$ for carbon, water ice, and organics, and a factor of $10^2$ for silicate, silicon carbide, and iron. We conclude the surface curvature of the particles is a quantity of great importance to the small particle effect, unless the particles are submicrometers in radius or larger.",
  "split": "TRAIN"
}
{
  "judge": 3,
  "set": "arxiv",
  "task": "detect",
  "packet_index": 63,
  "id": "1008.1766-8",
  "system_a": "null",
  "system_b": "charswap",
  "edit_a": "We prove that optimal point-to-point codes are unsuitable for soft-IC, as well as for all strategies that apply partial decoding to improve upon single-user detection (SUD) and multiuser detection (MUD), including Han-Kobayashi (HK).",
  "edit_b": "We prove that optimal poitt-to-point codes are unsuitable for soft-IC, as wwll as for all strategoes that apply partial decoding to improve upon single-user detection (SUD) and multiuser detection (MUD), including Han-Kobayashi (HK).",
  "original": "We prove that optimal point-to-point codes are unsuitable for soft-IC, as well as for all strategies that apply partial decoding to improve upon single-user detection (SUD) and multiuser detection (MUD), including Han-Kobayashi (HK).",
  "previous_sentence": "To analyze soft-IC, we adapt existing techniques for iterative multiuser detection, and focus on binary-input additive white Gaussian noise (BIAWGN) interference channels.",
  "next_sentence": "",
  "judgment": "b",
  "abstract": "We provide a rigorous mathematical analysis of two communication strategies: soft decode-and-forward (soft-DF) for relay channels, and soft partial interference-cancelation (soft-IC) for interference channels. Both strategies involve soft estimation, which assists the decoding process. We consider LDPC codes, not because of their practical benefits, but because of their analytic tractability, which enables an asymptotic analysis similar to random coding methods of information theory. Unlike some works on the closely-related demodulate-and-forward, we assume non-memoryless, code-structure-aware estimation. With soft-DF, we develop {\\it simultaneous density evolution} to bound the decoding error probability at the destination. This result applies to erasure relay channels. In one variant of soft-DF, the relay applies Wyner-Ziv coding to enhance its communication with the destination, borrowing from compress-and-forward. To analyze soft-IC, we adapt existing techniques for iterative multiuser detection, and focus on binary-input additive white Gaussian noise (BIAWGN) interference channels. We prove that optimal point-to-point codes are unsuitable for soft-IC, as well as for all strategies that apply partial decoding to improve upon single-user detection (SUD) and multiuser detection (MUD), including Han-Kobayashi (HK).",
  "split": "TEST"
}
{
  "judge": 2,
  "set": "arxiv",
  "task": "detect",
  "packet_index": 393,
  "id": "hep-ph/0407217-1",
  "system_a": "viper",
  "system_b": "mt",
  "edit_a": "We present the general expression for nine double-polarization forward-backward asymmetries\u2024",
  "edit_b": "Here is the general expression for nine double-polarization asymmetries and forth.",
  "original": "We present the general expression for nine double-polarization forward-backward asymmetries.",
  "previous_sentence": "We study the doubly-polarized lepton pair forward-backward asymmetries in (Lambda_b -> Lambda l^+ l^-) decay using a general, model independent form of the effective Hamiltonian.",
  "next_sentence": "It is observed that, the study of the forward-backward asymmetries of the doubly-polarized lepton pair is a very useful tool for establishing new physics beyond the standard model.",
  "judgment": "b",
  "abstract": "We study the doubly-polarized lepton pair forward-backward asymmetries in (Lambda_b -> Lambda l^+ l^-) decay using a general, model independent form of the effective Hamiltonian. We present the general expression for nine double-polarization forward-backward asymmetries. It is observed that, the study of the forward-backward asymmetries of the doubly-polarized lepton pair is a very useful tool for establishing new physics beyond the standard model. Moreover, the correlation between forward-backward asymmetry and branching ratio is investigated. It is shown that there exist certain certain regions of the new Wilson coefficients where new physics can be established by measuring the polarized forward-backward asymmetry only.",
  "split": "TRAIN"
}
{
  "judge": 3,
  "set": "reddit",
  "task": "detect",
  "packet_index": 238,
  "id": "7s8hbk-2",
  "system_a": "null",
  "system_b": "mt",
  "edit_a": "I am monitoring ebay for broken LTE surface 3s, but nothing yet.",
  "edit_b": "I am monitoring ebay for 3s LTE broken surface, but nothing yet.",
  "original": "I am monitoring ebay for broken LTE surface 3s, but nothing yet.",
  "previous_sentence": "I have gone to Microsoft, but the only option they give is the $310 out of warranty replacement for the whole surface, which is a bit insane for the problem at hand.",
  "next_sentence": "",
  "judgment": "b",
  "abstract": "Does anyone know where you could get a replacement for the SIM card tray for the surface 3? I have gone to Microsoft, but the only option they give is the $310 out of warranty replacement for the whole surface, which is a bit insane for the problem at hand. I am monitoring ebay for broken LTE surface 3s, but nothing yet.",
  "split": "TRAIN"
}
{
  "judge": 4,
  "set": "arxiv",
  "task": "meaning",
  "packet_index": 251,
  "id": "1209.2821-2",
  "system_a": "vae",
  "system_b": "mt",
  "edit_a": "Our numerical model suggest evidence of packing simulations for different values for the $ - $ roughness $ p $ as well to the samples is shown to to be to the $ $ $.",
  "edit_b": "Our experimental data provide evidence that size estimates produce reasonable values \u200b\u200bfor the focal point diameter $ d $, provided that the samples are carefully characterized with respect to local electronic parameters.",
  "original": "Our experimental data give evidence that size estimates yield reasonable values for the point-contact diameter $d$ as long as the samples are carefully characterized with respect to the local electronic parameters.",
  "previous_sentence": "Direct measurements of the nanocontact size by scanning electron microscopy allow a comparison with theoretical models for contact-size estimates of heterocontacts.",
  "next_sentence": "",
  "judgment": "b",
  "abstract": "Nanostructured superconductor/ferromagnet heterocontacts are studied in the different transport regimes of point-contact spectroscopy. Direct measurements of the nanocontact size by scanning electron microscopy allow a comparison with theoretical models for contact-size estimates of heterocontacts. Our experimental data give evidence that size estimates yield reasonable values for the point-contact diameter $d$ as long as the samples are carefully characterized with respect to the local electronic parameters.",
  "split": "TRAIN"
}
{
  "judge": 5,
  "set": "arxiv",
  "task": "detect",
  "packet_index": 342,
  "id": "1107.1857-5",
  "system_a": "viper",
  "system_b": "scpn",
  "edit_a": "Nuclei with initial mass >~10^10g (Pc/10^6 (dyne/cm^2) sec (phi))^3 are fully ablated before exploding, though the ho\u1e6d wake itself explodes.",
  "edit_b": "First the name of the first part of 10 ^ 10g pc is replaced by the end of the first time in the explosion of the upper part of the sound of in accordance with in view of",
  "original": "Nuclei with initial mass >~10^10g (Pc/10^6 (dyne/cm^2) sec (phi))^3 are fully ablated before exploding, though the hot wake itself explodes.",
  "previous_sentence": "Larger masses (>10^11g) with small perihelion (q<1.01Rsun) ablation dominates but results are sensitive to nucleus strength, Pc, and entry angle to the vertical, phi.",
  "next_sentence": "For most sun-impactors sec(phi)~1.",
  "judgment": "b",
  "abstract": "[Abridged] Sun-grazing comets almost never re-emerge, but their sublimative destruction near the sun has only recently been observed directly, while chromospheric impacts have not yet been seen, nor impact theory developed. Employing simple analytic models to describe comet destruction near the Sun and to enable the estimation of observable signatures, we find analytic solutions for the mass as a function of distance from the Sun, for insolation sublimation, impact ablation and explosion. Sun-grazers are found to fall into three regimes based on initial mass and perihelion: sublimation-, ablation-, and explosion-dominated. Most sun-grazers are destroyed sublimatively, and our analytic results are similar to numerical models. Larger masses (>10^11g) with small perihelion (q<1.01Rsun) ablation dominates but results are sensitive to nucleus strength, Pc, and entry angle to the vertical, phi. Nuclei with initial mass >~10^10g (Pc/10^6 (dyne/cm^2) sec (phi))^3 are fully ablated before exploding, though the hot wake itself explodes. For most sun-impactors sec(phi)~1. For small perihelion the ablation regime applies to moderate masses ~10^13-16 g impactors unless Pc is very low. For higher masses, or smaller perihelia, nuclei reach higher densities where ram pressure causes catastrophic explosion. For perihelion < 1.01Rsun, initial mass > 10^11 g nuclei are destroyed by ablation or explosion (depending on phi and Pc) in the chromosphere, producing flare-like events with cometary abundance spectra. For all plausible masses and physical parameters, nuclei are destroyed above the photosphere.",
  "split": "TRAIN"
}
{
  "judge": 2,
  "set": "reddit",
  "task": "meaning",
  "packet_index": 160,
  "id": "7u6cc5-1",
  "system_a": "addcos",
  "system_b": "viper",
  "edit_a": "bullion prices recovered lows to trade within a rigid range as traders anticipated further trend ahead of the european central bank meeting , and us economic growth data this week .",
  "edit_b": "Gold prices recovered lows to trade within a rigid \u1e5fange as traders anticipated further trend ahead of the European Central Bank meeting, and US economic growth data this week.",
  "original": "Gold prices recovered lows to trade within a rigid range as traders anticipated further trend ahead of the European Central Bank meeting, and US economic growth data this week.",
  "previous_sentence": "Gold traded higher as a fall in dollar and US treasury yields increased demand for the yellow metal.",
  "next_sentence": "Dollar and US treasury yields weakness, meanwhile, supporting upward momentum in the precious metal was balanced a little by falling safe-haven demand amid a lack of geopolitical tensions.",
  "judgment": "b",
  "abstract": "Gold traded higher as a fall in dollar and US treasury yields increased demand for the yellow metal. Gold prices recovered lows to trade within a rigid range as traders anticipated further trend ahead of the European Central Bank meeting, and US economic growth data this week. Dollar and US treasury yields weakness, meanwhile, supporting upward momentum in the precious metal was balanced a little by falling safe-haven demand amid a lack of geopolitical tensions. The rise in gold prices come as the US government shutdown came to end late Monday after the U.S. Senate voted to pass a temporary spending plan through Feb. 8. Technical outlook : Gold daily chart has formed \"Rising wedge\u201d pattern. The last session ended up bullish retesting the channel\u2019s support slope line. The market is expected continue on the same trend along with a small correction over the negative side, testing all the way through $1345-1350(30010-30135) levels in the upcoming sessions. Alternatively, if the market breaks below the Support level holding at $1335(29760) then it might continue in bearish. The downside rally could test $1330-1325(29635-29510). Resistance holds at $1350(30135).",
  "split": "TRAIN"
}
{
  "judge": 4,
  "set": "arxiv",
  "task": "detect",
  "packet_index": 43,
  "id": "1510.01333-4",
  "system_a": "viper",
  "system_b": "addcos",
  "edit_a": "Our analysis of the reprocessed emission show that 3C 390.3 only has a small amount of reflection (R~0.3\u00a1, and of that the vast majority is from distant neutral matter.",
  "edit_b": "our analysis of the reprocessed emission show that 3c 390.3 only has a small quantity of reflection ( r ~ 0.3 ) , and of that the vast majority is from distant neutral matter .",
  "original": "Our analysis of the reprocessed emission show that 3C 390.3 only has a small amount of reflection (R~0.3), and of that the vast majority is from distant neutral matter.",
  "previous_sentence": "Expanding our study of the Comptonization spectrum to the optical/UV by studying the simultaneous Swift-UVOT data, we find indications that the compactness of the corona allows only a small fraction of the total UV/optical flux to be Comptonized.",
  "next_sentence": "However we also discover a soft X-ray excess in the source, which can be described by a weak ionized reflection component from the inner parts of the accretion disk.",
  "judgment": "b",
  "abstract": "We present the results from a joint Suzaku/NuSTAR broad-band spectral analysis of 3C 390.3. The high quality data enables us to clearly separate the primary continuum from the reprocessed components allowing us to detect a high energy spectral cut-off ($E_\\text{cut}=117_{-14}^{+18}$ keV), and to place constraints on the Comptonization parameters of the primary continuum for the first time. The hard over soft compactness is 69$_{-24}^{+124}$ and the optical depth 4.1$_{-3.6}^{+0.5}$, this leads to an electron temperature of $30_{-8}^{+32}$ keV. Expanding our study of the Comptonization spectrum to the optical/UV by studying the simultaneous Swift-UVOT data, we find indications that the compactness of the corona allows only a small fraction of the total UV/optical flux to be Comptonized. Our analysis of the reprocessed emission show that 3C 390.3 only has a small amount of reflection (R~0.3), and of that the vast majority is from distant neutral matter. However we also discover a soft X-ray excess in the source, which can be described by a weak ionized reflection component from the inner parts of the accretion disk. In addition to the backscattered emission, we also detect the highly ionized iron emission lines Fe XXV and Fe XXVI.",
  "split": "TEST"
}
```

Please cite the dataset by citing the paper describing it:
```
@inproceedings{merkhofer-etal-2021-perceptual,
    title = "Perceptual Models of Machine-Edited Text",
    author = "Merkhofer, Elizabeth  and
      Mendoza, Monica-Ann  and
      Marvin, Rebecca  and
      Henderson, John",
    booktitle = "Findings of the Association for Computational Linguistics: ACL-IJCNLP 2021",
    month = aug,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.findings-acl.342",
    doi = "10.18653/v1/2021.findings-acl.342",
    pages = "3909--3920",
}
```


Point of Contact:
Elizabeth Merkhofer
emerkhofer@mitre.org

---
The HPMET Dataset is distributed under an Apache License Version 2.0. 

Approved for Public Release; Distribution Unlimited.  
Public Release Case Number 21-0320.  
©2021 The MITRE Corporation. ALL RIGHTS RESERVED.  
