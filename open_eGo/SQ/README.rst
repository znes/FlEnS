
renpassG!S status quo scenario of the open_eGo project. The scenario is derived from the ENTSO-E Ten-Year-Network-Development-Plan (TYNDP) which serves as a base for the German Netzentwicklungsplan (NEP).
There are `licensing issues <http://open-power-system-data.org/legal>`_ due to the ENTSO-E data. The data will be published if these are cleared.

**Table of Contents**

.. contents::
    :depth: 1
    :local:
    :backlinks: top
.. sectnum::

Compatibility
=============

renpass_gis v0.1

Documentation
=============

ToDo
~~~~

* Validation
* Other renewable not included.
* Biomass source in DE. (?)

Regions
~~~~~~~

Germany and countries that have a direct electrical connection with Germany.

AT, CH, CZ, DE, DK, FR, LU, NL, PL, SE

Fuel prices & CO2 costs
~~~~~~~~~~~~~~~~~~~~~~~

European Countries
~~~~~~~~~~~~~~~~~~

+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|Fuel        |Fuel price €2014/GJ          |Source         |Emission tCO2/GJ  |Source     |Fuel price including CO2 cost €2014/MWh|
+============+=============================+===============+==================+===========+=======================================+
|gas         |8.0866                       |Kohlenstatistik|0.0559            |UBA2015_   | 30.3012                               |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|hard_coal   |2.4908                       |Ibid.          |0.0934            |Ibid.      | 10.9541                               |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|oil         |10.5433                      |Ibid.          |0.0733            |Ibid.      | 39.5156                               |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|waste       |1.86                         |Ibid.          |0.0917            |IPCC2006_  | 8.6470                                |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|biomass     |5.56                         |PROGNOS2013_   |0.0020            |DEFRA2012_ | 20.0586                               |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|lignite     |1.15                         |ISI2011_       |0.1051            |UBA2015_   | 6.3761                                |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|uranium     |1.11                         |Ibid.          |0.0088            |OEKO2007_  | 4.1832                                |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+
|mixed_fuels |1.86                         |nan            |0.0917            |nan        | 8.6470                                |
+------------+-----------------------------+---------------+------------------+-----------+---------------------------------------+

with CO2 price = 5.91 EUR/tCO2 (EEX)
with 3.6 GJ ~ 1 MWh

Manipulations:
- BMU-DLR2012_: Linear interpolated in the timeframe from 2010 to 2015, inflation - adjusted
- mixed fuels same values as waste

Variable costs
~~~~~~~~~~~~~~

+-----------+----------+---------------+
|Type       | €/MWh    |Source         |
+===========+==========+===============+
|gas        | 2.0      | IER2010_      |
+-----------+----------+---------------+
|hard_coal  | 4.0      | Ibid.         |
+-----------+----------+---------------+
|oil        | 1.5      | DIW2013_      |
+-----------+----------+---------------+
|waste      | 23.0     | Energynet2012_|
+-----------+----------+---------------+
|biomass    | 3.9      | Ibid.         |
+-----------+----------+---------------+
|lignite    | 4.4      | IER2010_      |
+-----------+----------+---------------+
|uranium    | 0.5      | Ibid.         |
+-----------+----------+---------------+
|mixed_fuels| 23.0     | nan           |
+-----------+----------+---------------+

Fixed costs
~~~~~~~~~~~

+-----------+----------+---------------+
|Type       | €/MW     | Source        |
+===========+==========+===============+
|gas        | 19,000   | IER2010_      |
+-----------+----------+---------------+
|hard_coal  | 35,000   | Ibid.         |
+-----------+----------+---------------+
|oil        |  6,000   | DIW2013_      |
+-----------+----------+---------------+
|waste      | 16,500   | Energynet2012_|
+-----------+----------+---------------+
|biomass    | 29,000   | Ibid.         |
+-----------+----------+---------------+
|lignite    | 39,000   | IER2010_      |
+-----------+----------+---------------+
|uranium    | 55,000   | Ibid.         |
+-----------+----------+---------------+
|mixed_fuels| 16,500   | nan           |
+-----------+----------+---------------+

Efficiencies
~~~~~~~~~~~~

+-----------+-------+----------------+
|Type       |eta    |Source          |
+===========+=======+================+
|gas        | 42.5  |ENTSOE2014c     |
+-----------+-------+----------------+
|hard_coal  | 38.0  | Ibid.          |
+-----------+-------+----------------+
|oil        | 34.0  | Ibid.          |
+-----------+-------+----------------+
|waste      | 26.0  | Ibid.          |
+-----------+-------+----------------+
|biomass    | 38.0  | Ibid.          |
+-----------+-------+----------------+
|lignite    | 38.0  | Ibid.          |
+-----------+-------+----------------+
|uranium    | 32.5  | Ibid.          |
+-----------+-------+----------------+
|mixed_fuels| 26.0  | Ibid.          |
+-----------+-------+----------------+

- Based on efficiency classes provided by ENTSOE2014c_ average values are assumed
- Mixed fuels same values as waste

Installed capacities
~~~~~~~~~~~~~~~~~~~~

Germany
_______

Conventional power plants
+++++++++++++++++++++++++

- Source: NEP2015a_
- Description: Kraftwerksliste zum Entwurf Szenariorahmen NEP/O-NEP 2015
- Year: 2014
- Manipulations: See OPENEGO_ / OEP_.

Renewable power plants
++++++++++++++++++++++

- Source: ENERGYMAP2015_, BNETZA2015_
- Description: Independent and administrative renewable power plant register.
- Year: 2015
- Manipulations: See OPENEGO_ / OEP_.

Installed generation capacity aggregated by source in Germany:

+-------------+----------------+
|Source       | GW             |
+=============+================+
|gas          | 27.9           |
+-------------+----------------+
|hard_coal    | 31.5           |
+-------------+----------------+
|oil          |  4.5           |
+-------------+----------------+
|waste        |  1.7           |
+-------------+----------------+
|biomass      |  7.2           |
+-------------+----------------+
|lignite      | 22.9           |
+-------------+----------------+
|uranium      | 12.0           |
+-------------+----------------+
|mixed_fuels  |  2.6           |
+-------------+----------------+
|wind_onshore | 41.3           |
+-------------+----------------+
|wind_offshore|  5.6           |
+-------------+----------------+
|solar        | 38.5           |
+-------------+----------------+
|run_of_river |  3.9           |
+-------------+----------------+
|reservoir    |  1.4           |
+-------------+----------------+

Installed storage capacity aggregated by source in Germany

+-------------+----------------+
|Source       | GW             |
+=============+================+
|pumped_hydro |  9.3           |
+-------------+----------------+

Other countries
_______________

- Source: ENTSOE2014a_
- Description: 19:00pm values, Scenario B (Best estimate) based on the expectations of the TSO, See "Source". Original Data has been provided by ENTSO-E.
- Year: 2014
- Manipulations: None

Availability
~~~~~~~~~~~~

The availability of thermal power plants is 85 %.

- Source: VGB PowerTech. Verfügbarkeit von Wärmekraftwerken 2003-2012,“ Essen, 2013.

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

- Source: MARTINEZ-ANIDO2013_, p.149 ff
- Description: See "Source". Original Data has been provided by ENTSO-E (NTC Matrix)
- Year: 2010
- Manipulations: None

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

Reservoir Timeseries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Power generation by reservoirs is restricted by the maximum annual full-load-hours of 2419. Derived from EON2010_. Additionally in each timestep the maximum power output corresponds to the national load curve. Thus maximum capacity can just be used at peak demand.






.. _locations: https://github.com/znes/cFlEnS/blob/feature/open_eGo/open_eGo/modelpowerplants.geojson

..  * "BMWI Energie Daten - Factors, Sheet 0.2 and 0.3":https://www.bmwi.de/BMWi/Redaktion/Binaer/energie-daten-gesamt,property=blob,bereich=bmwi2012,sprache=de,rwb=true.xls
..  * "DIW2013":https://www.diw.de/documents/publikationen/73/diw_01.c.424566.de/diw_datadoc_2013-068.pdf

.. _MARTINEZ-ANIDO2013 : http://ses.jrc.ec.europa.eu/sites/ses.jrc.ec.europa.eu/files/documents/thesis_brancucci_electricity_without_borders.pdf
.. _ISI2011: http://www.isi.fraunhofer.de/isi-wAssets/docs/x/de/publikationen/Final_Report_EU-Long-term-scenarios-2050_FINAL.pdf
.. _UBA2015: https://www.umweltbundesamt.de/themen/klima-energie/treibhausgas-emissionen
.. _IPCC2006: http://www.ipcc-nggip.iges.or.jp/public/2006gl/pdf/2_Volume2/V2_2_Ch2_Stationary_Combustion.pdf
.. _DEFRA2012: https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/69554/pb13773-ghg-conversion-factors-2012.pdf
.. _EON2010: http://apps.eon.com/documents/EWK_Walchensee_2010_ger.pdf
.. _OEKO2007: http://www.oeko.de/oekodoc/318/2007-008-de.pdf
.. _PROGNOS2013: http://www.prognos.com/uploads/tx_atwpubdb/131010_Prognos_Belectric_Studie_Freiflaechen_Solarkraftwerke_02.pdf
.. _ECOFYS2014: http://www.ecofys.com/files/files/ecofys-2014-international-comparison-fossil-power-efficiency.pdf
.. _IER2010: http://www.ier.uni-stuttgart.de/publikationen/arbeitsberichte/downloads/Arbeitsbericht_08.pdf
.. _DIW2013: https://www.diw.de/documents/publikationen/73/diw_01.c.424566.de/diw_datadoc_2013-068.pdf
.. _Energynet2012: https://www.energinet.dk/SiteCollectionDocuments/Danske%20dokumenter/Forskning/Technology_data_for_energy_plants.pdf
.. _BMU-DLR2012: http://www.dlr.de/dlr/Portaldata/1/Resources/bilder/portal/portal_2012_1/leitstudie2011_bf.pdf
.. _IRENA2015: http://www.irena.org/DocumentDownloads/Publications/IRENA_REmap_Germany_report_2015.pdf
.. _ENTSOE2014a: https://www.entsoe.eu/Documents/SDC%20documents/SOAF/140602_SOAF%202014_dataset.zip
.. _ENTSOE2014b: https://www.entsoe.eu/major-projects/ten-year-network-development-plan/maps-and-data/Pages/default.aspx
.. _ENTSOE2014c: https://www.entsoe.eu/major-projects/ten-year-network-development-plan/tyndp-2014/Documents/TYNDP2014%20market%20modelling%20data.xlsx
.. _Bundesbank: https://www.bundesbank.de/Redaktion/DE/Downloads/Statistiken/Aussenwirtschaft/Devisen_Euro_Referenzkurs/stat_eurefd.pdf?__blob=publicationFile
.. _NEP2015a: http://www.netzentwicklungsplan.de/system/files/media/documents/20140430_Entwurf_NEP2015_KW-Liste.pdf
.. _ENERGYMAP2015: http://www.energymap.info/download.html 
.. _BNETZA2015: https://www.bundesnetzagentur.de/SharedDocs/Downloads/DE/Sachgebiete/Energie/Unternehmen_Institutionen/ErneuerbareEnergien/Anlagenregister/VOeFF_Anlagenregister/2016_01_Veroeff_AnlReg.xlsx?__blob=publicationFile&v=2
.. _OPENEGO: https://github.com/openego
.. _OEP: http://oep.iks.cs.ovgu.de/
.. _COASTDAT2: http://www.earth-syst-sci-data.net/6/147/2014/essd-6-147-2014.pdf
.. _FEEDINLIB2015: http://feedinlib.readthedocs.io/en/v0.0.7/
.. _Wiese2015: http://www.reiner-lemoine-stiftung.de/pdf/dissertationen/Dissertation_Frauke_Wiese.pdf




Contact
=======

Martin Soethe (University of Flensburg): <martin.soethe(at)uni-flensburg.de>

Citation
========

Licence
=======

As mentioned above, there are currently some licensing issues due to the ENTSO-E data. The data will be published under a suitable license if these are cleared.
