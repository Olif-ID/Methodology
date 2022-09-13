# Methodology

### 1. Creating the Library

Before mapping fragrant materials to Urbit address space we established 4 guidelines pertaining to fragrance and the construction of a material library.
<br/>
<br/>

>1 - Establish a library with wide ranging representation of various odor categories <br/>
2 - Limit the material library to be manageable for an enthusiast (~100 pcs) <br/>
3 - Only use fragrant materials that can be regularly acquired (insist upon CAS#) <br/>
4 - Only use fragrant materials that have saftey documentation
<br/>

Using these guidlines we created a material library of 96 ingredients divided into 16 odor groups. Our odor groups were prepared using two properties. First, oganization by similar olfactive properties; second, agreeability with neighboring odor group ingredients.
<br/>
<br/>

| Odor Group | Materials                                        |
|------------|:-------------------------------------------------|
| Wood       |  Virginia Cedarwood, Anthamber, Patchouli, Hinoki, Sanderol, Okoumal | 
| Citrus     |  Bergamot, Lemon, Sweet Orange, Petitgrain, Bitter Yuzu, Pink Grapefruit |
| Herbal     |  Lavandin, Juniper Berry, Spanish Sage, Rosemary, Myrcene, Carene 3 Delta |
| Floral     |  Phenyl Ethyl Alcohol, Geraniol, Rose Absolute, Cyclamen Aldehyde, PADMA, Florhydral |
| Earth      |  Geosmin, Herbal Pyrane, Clearwood, Evernyl, Summer Savory, Borneol |
| Spice      |  Eugenol, Frankincense, Cardamom, Black Pepper, Coffee, Cassia |
| Terpene    |  PO Cedarwood, Balsam Fir Needle, Siberian Fir Needle, Isobornyl Acetate, Black Pine, Cypress |
| Musk       |  Romandolide, Ethylene Brassylate, Isoambrettolide, Galaxolide, Ambroxan, Cetalox |
| Vanilla    |  Vanillin, Beeswax Absolute, Coumarin, Heliotropine, Labdanum, Methyl Liatone |
| Narcotic   |  Jasmin Sambac, Neroli, Magnolia, Hedione, Ylang Ylang, MA/Triplal Shiff Base |
| Resin      |  Tonka, Olibanum, Palo Santo, Myrrh, Elemi, Copaiba Blasam |
| Menthol    |  Myrtle, Laurel, Helichrysum, Peppermint, Eucalyptus, Tea Tree |
| Fruit      |  Fructone, Firascone, Respberry Ketone, Gamma Octalactone, Gamma Decalactone, Aldehyde C-16 |
| Green      |  Triplal, Galbanum, Gardenol, Stemone, Cis-3 Hexonol, Violet Leaf Absolute |
| Smoke      |  Cypriol, Vetiver, Safraeline, Birch Tar, Amyris, Tobacco Leaf |
| Aquatic    |  Tropional, Calone, Floralozone, Dihydromyrcenol, melonal, vetival |
<br/>
<br/>
<br/>

### 2. Mapping Library to Primitives
<br/>
Now that we have a library to build from, we begin with the same method used for @p and Sigil rendering by assigning unique material combinations to the 512 namespace primitives. (Examples of namespace primitives are phones for @ps or glyphs for sigils)
<br/>
<br/>

> **Namespace Primitives**<br/>
256 Suffixes (Galaxies) <br/>
256 Prefixes (Stars, Planets, Moons, Comets)<br/>
<br/>
To recreate all 512 Namespace Primitives using our library, we evenly distribute the 16 odor groups across them all, creating 16 suffixes and 16 prefixes for every odor group. With 96 total materials divided into 16 odor groups, every odor group has 6 materials used to create the 32 namespace primitives. 
<br/>
<br/>
To apply the 6 materials to each odor group's set of 32 primitives, we create 3 categories of mixture.
<br/>
<br/>

>**Pures** <br/>
4 suffixes per odor group.<br/>
These mixtures are 100% of 1 material. <br/>
Pures utilize 4 of the 6 alloted materials and best represent the odor group they are in and have the least amount of usage restrictions.

>**Hearts** <br/>
12 suffixes per odor group. <br/>
These mixtures use two materials at ratios between 1:1 and 4:1. <br/>
Hearts utilize between 4 and 6 of the 6 alloted materials

>**Modifiers** <br/>
16 Prefixes per odor group <br/>
These mixtures use two materials at ratios between 5:1 and 50:1. <br/>
Modifiers serve as a home for materials with qualities that prevent them from use in large concentration.

To find out which **materials** should be made available to each category of **mixture** we used two properties, **Usage limitation** and **Relative Susbstantivity**.


>**Usage limitation**
Usage Limitation is a property derived from IFRA restrictions on the quantities of fragrant materials used in consumer products. These restictions refer to specific cielings of usage (by percentage) in a final use product. To calculate our usage limitation we set a maximum **fragrance load** of 20% which allows for Eau De Parfum concentration of fine fragrances.

>**Relative substantivity**
Relative substantivity is a subjective property given to each material that imparts a level of power and reception by the nose. This number creates a posture amoungst its peer materials. The number 1 is a baseline and is assigned to the material Virginia Cedarwood (CAS# 8000-27-9). Materials are given an RS score logrithmically in comparison to the baseline when smelling. Ex: If something smells "twice as much" in power, it's assigned a 2. If something smells "half as much" in power, it's assigned a 0.5
<br/>
<br/>

### 3. Building complex address space with Olif primitives
<br/>
Now that all namespace primitives have been assigned materials and unique percentages, we create a system for combining the primitives with one another to form higher level addresses. One constraint we deal with in fragrance is a lack of ordinal dimension. @p's and sigils have the advantage of placing their primitives in sequence with one another to help distinguish identity and maintain a unique rendering.

To accomplish some sense of ordinal dimension in an Olif, we apply weighted percentages to primitives when adding them together.

Galaxy: ~aaa <br/>
aaa: 100% <br/>

Star: ~aaabbb <br/>
aaa: 66.6% <br/>
bbb: 33.3% <br/>

Planet: ~aaabbb-cccddd <br/>
aaa: 50% <br/>
bbb: 25% <br/>
ccc: 12.5% <br/>
ddd: 12.5% <br/>
