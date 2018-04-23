**eGo100**. A 100 % renewable energy scenario based on ZNES base scenario 2050 created by Marion Crist originally derived from the ehighway2016_ scenario x-7: 100% RES electricity. There are no conventional power plants in Germany. Contains ENTSOE data and currently cannot be published.




.. contents:: `Table of contents`
    :depth: 1
    :local:
    :backlinks: top
.. sectnum::

Compatibility
=============

renpass_gis v0.1 
See more on renpassgis_ requirements. 

Documenation
============

ToDo
~~~~

* Validation
* Demand: Annual maximum addjusted to maximum data from ehighway2016_ (?)
* rounding error run of river NEP 2035 4200 MW

Regions
~~~~~~~

'AT', 'CH', 'CZ', 'DE', 'DK', 'FR', 'LU', 'NL', 'PL', 'SE'

Fuel prices & CO2 costs
~~~~~~~~~~~~~~~~~~~~~~~

European Countries
~~~~~~~~~~~~~~~~~~

+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|Fuel        |Fuel price €2014/GJ          |Source         |Emission tCO2/GJ  |Source     |Fuel price including CO2 cost €2014/MWh|
+============+=============================+===============+==================+===========+=======================================+
|gas         |11.54                        |BMU-DLR2012_   |0.0559            |UBA2015_   | 54.0533                               |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|biomass     |7.58                         |PROGNOS2013_   |0.0020            |DEFRA2012_ | 27.7348                               |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+


with CO2 price = 62.05 EUR/tCO2 (BMU-DLR2012_)
with 3.6 GJ ~ 1 MWh

Calculation factors:

+-------+---------------+---------------+-----------+------------+
|1      |GJ             |0.0341208424   |t SKE      |            |
+-------+---------------+---------------+-----------+------------+
|1      |t SKE          |29.3076        |GJ         |            |
+-------+---------------+---------------+-----------+------------+
|1      |EURO_2014      |1.3285         |US $ _ 2014|Bundesbank_ |
+-------+---------------+---------------+-----------+------------+
|1      |Mwh            |3.6            |GJ         |            |
+-------+---------------+---------------+-----------+------------+
|1      |bbl            |5.86152        |GJ         |            |
+-------+---------------+---------------+-----------+------------+

Manipulations:
- BMU-DLR2012_: Linear interpolated in the timeframe from 2010 to 2015, inflation - adjusted


Variable costs
~~~~~~~~~~~~~~

+-----------+----------+---------------+
|Type       | €/MWh    |Source         |
+===========+==========+===============+
|gas        | 2.0      | IER2010_      |
+-----------+----------+---------------+
|biomass    | 3.9      | Ibid.         |
+-----------+----------+---------------+

Fixed costs
~~~~~~~~~~~

+-----------+----------+---------------+
|Type       | €/MW     | Source        |
+===========+==========+===============+
|gas        | 19,000   | IER2010_      |
+-----------+----------+---------------+
|biomass    | 29,000   | Ibid.         |
+-----------+----------+---------------+

Efficiencies
~~~~~~~~~~~~

+-----------+-------+----------------+
|Type       |eta    |Source          |
+===========+=======+================+
|gas        | 42.5  |ENTSOE2014c_    |
+-----------+-------+----------------+
|biomass    | 38.0  | Ibid.          |
+-----------+-------+----------------+

- Based on efficiency classes provided by ENTSOE2014c_ average values are assumed

Efficiencies Storage capacities
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

+--------------+--------------+----------------+-----------+--------------------+
| Technology   | Cebulla2015_ | Energynet2012_ | AEE2012_  | scenario znes_2050 |
+==============+==============+================+===========+====================+
| pumped hydro | 82.81        | 70-80          | 65-85     | 80                 |
+--------------+--------------+----------------+-----------+--------------------+
| a_caes       | 72.98        | \-             | 62-70     | 70                 |
+--------------+--------------+----------------+-----------+--------------------+
| hydrogen     | 46.5         | 35             | 20-40     | 40                 |
+--------------+--------------+----------------+-----------+--------------------+
| lithium_ion  | 94.09        | \-             | 90-95     | 95                 |
+--------------+--------------+----------------+-----------+--------------------+
| redox_flow   | 84.64        | 70             | 70-80     | 75                 |
+--------------+--------------+----------------+-----------+--------------------+


Installed capacities
~~~~~~~~~~~~~~~~~~~~

- Source: ehighway2016_, BNetzA2014_, energymap2014_, Cebulla2015_
- Description: Scenario X-7: 100% RES electricity
- Year: 2050
- Manipulations:

  - Germany no installed capacity for Gas. (100% RE in Germany).
  - In case of Germany the data for installed capacity of geothermal power plants is taken from the Leitstudie2012_. For neighbouring countries it is taken from the ISI2011b_ longterm study.
  - Data for run of river is completed based on the BNetzA2014_.
  - Data with regard to the future installed capacities of the storage types a_caes, hydrogen, lithium_ion, redox_flow is based on Cebulla2015_. The storage capacity of pumped storage power plants is taken from JRC2013_. (Scenario T1: using existing reservoirs, for DE, LU, NL, PL assumption of 10 hours discharge duration (1kW installed = 1kWh storage capacity)). For a_caes, hydrogen, lithium_ion and redox_flow the storage capacity is calculated with own assumed discharce duration (h) based on ehighwayCaes2014_ (p.8).

+--------------+--------------------------+
|country       |pumped_hydro GWh JRC2013_ | 
+==============+==========================+
|AT            | 443                      |
+--------------+--------------------------+
|BE            | 12                       |
+--------------+--------------------------+
|CH            | 1656                     |
+--------------+--------------------------+
|CZ            | 39                       |
+--------------+--------------------------+
|DE            | 127.9                    |
+--------------+--------------------------+
|DK            | 0                        |
+--------------+--------------------------+
|FR            | 1184                     |
+--------------+--------------------------+
|LU            | 18                       |
+--------------+--------------------------+
|NL            | 1.04                     |
+--------------+--------------------------+
|NO            | 991                      |
+--------------+--------------------------+
|PL            | 37.9                     |
+--------------+--------------------------+
|SE            | 0                        |
+--------------+--------------------------+

Own assumptions for storage duration time based on ehighwayCaes2014_

+--------------+--------------+
| Technology   | duration (h) |
+--------------+--------------+
| a_caes       | 3            |
+--------------+--------------+
| hydrogen     | 10           |
+--------------+--------------+
| lithium_ion  | 5            |
+--------------+--------------+
| redox_flow   | 3.3          |
+--------------+--------------+


Runofriver installed capacity based on produced electricity from ehighway2016_ with an availability of 65% (5694 fullloadhours):

+--------------+-----------------------+------------------------+
|country       |ror GWh ehighway2016_  |ror GW_inst znes_2050   |
+==============+=======================+========================+
|AT            | 43857                 | 7.70                   |
+--------------+-----------------------+------------------------+
|BE            | 1770                  | 0.31                   |
+--------------+-----------------------+------------------------+
|CH            | 19353                 | 3.40                   |
+--------------+-----------------------+------------------------+
|CZ            | 2102                  | 0.37                   |
+--------------+-----------------------+------------------------+
|DE            | 24666                 | 4.33                   |
+--------------+-----------------------+------------------------+
|DK            | 69                    | 0.01                   |
+--------------+-----------------------+------------------------+
|FR            | 56656                 | 9.95                   |
+--------------+-----------------------+------------------------+
|LU            | 939                   | 0.16                   |
+--------------+-----------------------+------------------------+
|NL            | 754                   | 0.13                   |
+--------------+-----------------------+------------------------+
|NO            | 64545                 | 11.34                  |
+--------------+-----------------------+------------------------+
|PL            | 12023                 | 2.11                   |
+--------------+-----------------------+------------------------+
|SE            | 13929                 | 2.45                   |
+--------------+-----------------------+------------------------+


Availability
~~~~~~~~~~~~
Amount of biomass and hydro limited by fullloadhours from ehighway2016_ :

+--------------+-----------------------+------------------------+
|country       |fullloadhours biomass  |fullloadhours hydro     |
+==============+=======================+========================+
|AT            | 3406                  | 2007                   |
+--------------+-----------------------+------------------------+
|BE            | 2041                  | 0                      |
+--------------+-----------------------+------------------------+
|CH            | 3153                  | 2596                   |
+--------------+-----------------------+------------------------+
|CZ            | 3004                  | 1603                   |
+--------------+-----------------------+------------------------+
|DE            | 2514                  | 0                      |
+--------------+-----------------------+------------------------+
|DK            | 1260                  | 0                      |
+--------------+-----------------------+------------------------+
|FR            | 2913                  | 1838                   |
+--------------+-----------------------+------------------------+
|LU            | 0                     | 0                      |
+--------------+-----------------------+------------------------+
|NL            | 1928                  | 0                      |
+--------------+-----------------------+------------------------+
|NO            | 2744                  | 3165                   |
+--------------+-----------------------+------------------------+
|PL            | 2184                  | 0                      |
+--------------+-----------------------+------------------------+
|SE            | 1445                  | 3878                   |
+--------------+-----------------------+------------------------+

Demand
~~~~~~

Germany
_______

- Source: OPENEGO_
- Description: Synthetic data developed by the RLI in Berlin. Standard load profiles, OpenStreetMap and Zensus 2011 data were used.
- Year: -
- Manipulations: -

Other countries
_______________

- Source: http://data.open-power-system-data.org/time_series/2016-03-18/
- Description: See "Source". Original Data has been provided by ENTSO-E.
- Year: 2014
- Manipulations: Normalised by dividing the values of the respective country by their annual maximum.


Transshipment - Net Transfer Capacities (NTC)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Neighbouring countries:

- Source: ehighway2016_ Reinforced grid (based on planned grid until 2030 plus required grid for 100% RE 2050)

Germany capacities between dispatch regions:

- Source: Status quo from SciGRID2015_ plus planned capacities from ENLAG2009_ and BBPlG2013_
- Manipulations:

  - Grid requirements for 2050 from ehighway2016_ adjusted to German dispatch regions: north-south plus 4000 MW: dpr13-dpr17 plus 2000 MW and dpr13-dpr11 plus 2000 MW. west-east plus 6000 MW: dpr14-dpr01 plus 1000 MW and dpr03-dpr16 plus 5000 MW

Wind & Solar Timeseries
~~~~~~~~~~~~~~~~~~~~~~~

- Source: FEEDINLIB2015_, COASTDAT2_
- Description: Power plant models are configured as follows.

  **Windonshore**

  * wind_conv_type: ENERCON E 101 3000
  * h_hub: 129
  * d_rotor: 104

  **Windoffshore**

  * wind_conv_type: SIEMENS SWT 3.6 120
  * h_hub: 90
  * d_rotor: 120

  **Solar**

  * module_name: Yingli_YL210__2008__E__
  * azimuth: 180
  * tilt: 30
  * albedo: 0.2

- Weather Year: 2011
- Manipulations: A correction factor of 0.83 is applied on windoffshore, 0.8 on solar timeseries.

The following `locations`_ were used as starting point for feedinlib.

.. _locations: https://render.githubusercontent.com/view/geojson?url=https://raw.githubusercontent.com/znes/FlEnS/master/open_eGo/modelpowerplants.geojson




Reservoir Timeseries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Power generation by reservoirs is restricted by the maximum annual full-load-hours of 2419. Derived from EON2010_. Additionally in each timestep the maximum power output corresponds to the national load curve. Thus maximum capacity can just be used at peak demand.


Contact
=======

Marion Christ (University of Flensburg): <marion.christ@uni-flensburg.de>

Citation
========

Licence
=======

`**Open Data Commons Open Database License 1.0 (ODbL-1.0)** <https://opendatacommons.org/licenses/odbl/1.0/>`_
Copyright: © Europa-Universität Flensburg




..  * "BMWI Energie Daten - Factors, Sheet 0.2 and 0.3":https://www.bmwi.de/BMWi/Redaktion/Binaer/energie-daten-gesamt,property=blob,bereich=bmwi2012,sprache=de,rwb=true.xls
..  * "DIW2013":https://www.diw.de/documents/publikationen/73/diw_01.c.424566.de/diw_datadoc_2013-068.pdf

.. _MARTINEZ-ANIDO2013 : http://ses.jrc.ec.europa.eu/sites/ses.jrc.ec.europa.eu/files/documents/thesis_brancucci_electricity_without_borders.pdf
.. _ISI2011: http://www.isi.fraunhofer.de/isi-wAssets/docs/x/de/publikationen/Final_Report_EU-Long-term-scenarios-2050_FINAL.pdf
.. _UBA2015: https://www.umweltbundesamt.de/themen/klima-energie/treibhausgas-emissionen
.. _IPCC2006: http://www.ipcc-nggip.iges.or.jp/public/2006gl/pdf/2_Volume2/V2_2_Ch2_Stationary_Combustion.pdf
.. _DEFRA2012: https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/69554/pb13773-ghg-conversion-factors-2012.pdf
.. _OEKO2007: http://www.oeko.de/oekodoc/318/2007-008-de.pdf
.. _PROGNOS2013: http://www.prognos.com/uploads/tx_atwpubdb/131010_Prognos_Belectric_Studie_Freiflaechen_Solarkraftwerke_02.pdf
.. _ECOFYS2014: http://www.ecofys.com/files/files/ecofys-2014-international-comparison-fossil-power-efficiency.pdf
.. _IER2010: http://www.ier.uni-stuttgart.de/publikationen/arbeitsberichte/downloads/Arbeitsbericht_08.pdf
.. _DIW2013: https://www.diw.de/documents/publikationen/73/diw_01.c.424566.de/diw_datadoc_2013-068.pdf
.. _Energynet2012: https://www.energinet.dk/SiteCollectionDocuments/Danske%20dokumenter/Forskning/Technology_data_for_energy_plants.pdf
.. _BMU-DLR2012: http://www.dlr.de/dlr/Portaldata/1/Resources/bilder/portal/portal_2012_1/leitstudie2011_bf.pdf
.. _NEP2015: http://www.netzentwicklungsplan.de/NEP_2025_1_Entwurf_Kap_1_bis_3.pdf
.. _IRENA2015: http://www.irena.org/DocumentDownloads/Publications/IRENA_REmap_Germany_report_2015.pdf
.. _ENTSOE2014a: https://www.entsoe.eu/Documents/SDC%20documents/SOAF/140602_SOAF%202014_dataset.zip
.. _ENTSOE2014b: https://www.entsoe.eu/major-projects/ten-year-network-development-plan/maps-and-data/Pages/default.aspx
.. _ENTSOE2014c: https://www.entsoe.eu/major-projects/ten-year-network-development-plan/tyndp-2014/Documents/TYNDP2014%20market%20modelling%20data.xlsx
.. _Bundesbank: https://www.bundesbank.de/Redaktion/DE/Downloads/Statistiken/Aussenwirtschaft/Devisen_Euro_Referenzkurs/stat_eurefd.pdf?__blob=publicationFile
.. _ehighway2016: http://www.e-highway2050.eu/results/
.. _ONEP2014: http://www.netzentwicklungsplan.de/_NEP_file_transfer/ONEP_2014_2_Entwurf_Teil1.pdf 
.. _energymap2014: http://www.energymap.info/download/eeg_anlagenregister_2014.11.utf8.csv.zip
.. _BNetzA2014: http://www.bundesnetzagentur.de/DE/Sachgebiete/ElektrizitaetundGas/Unternehmen_Institutionen/Versorgungssicherheit/Erzeugungskapazitaeten/Kraftwerksliste/kraftwerksliste-node.html
.. _CoastDat2: http://www.earth-syst-sci-data.net/6/147/2014/essd-6-147-2014.pdf
.. _SciGRID2015: http://www.scigrid.de/
.. _ENLAG2009: http://www.gesetze-im-internet.de/bundesrecht/enlag/gesamt.pdf
.. _BBPlG2013: http://www.gesetze-im-internet.de/bundesrecht/bbplg/gesamt.pdf
.. _Feedinlib2015: http://feedinlib.readthedocs.io/en/v0.0.7/
.. _Wiese2015: http://www.reiner-lemoine-stiftung.de/pdf/dissertationen/Dissertation_Frauke_Wiese.pdf
.. _Cebulla2015: http://elib.dlr.de/96288/
.. _AEE2012: http://www.unendlich-viel-energie.de/media/file/160.57_Renews_Spezial_Strom_speichern_mar13_online.pdf
.. _JRC2013: https://ec.europa.eu/jrc/sites/jrcsh/files/jrc_20130503_assessment_european_phs_potential.pdf
.. _ehighwayCaes2014: http://www.e-highway2050.eu/fileadmin/documents/Results/D3/report_CAES.pdf
.. _Leitstudie2012: http://www.dlr.de/dlr/Portaldata/1/Resources/bilder/portal/portal_2012_1/leitstudie2011_bf.pdf
.. _ISI2011b: http://www.isi.fraunhofer.de/isi-de/x/projekte/314587_bmu-langfristszenarien.php
.. _renpassgis: https://github.com/znes/FlEnS/tree/features/ego-timeseries/open_eGo#requirements
.. _EON2010: http://apps.eon.com/documents/EWK_Walchensee_2010_ger.pdf
