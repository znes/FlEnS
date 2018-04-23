open_eGo scenario NEP_2035. The scenario is derived from the ENTSO-E Ten-Year-Network-Development-Plan (TYNDP) which serves as a base for the German Netzentwicklungsplan (NEP). There are `licensing issues <http://open-power-system-data.org/legal>`_ due to the ENTSO-E data. The data will be published if these are cleared.

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
* CHP < 10 MW as source. (?)

Regions
~~~~~~~

Germany and countries that have a direct electrical connection with Germany.

AT, CH, CZ, DE, DK, FR, LU, NL, PL, SE

Fuel prices & CO2 costs
~~~~~~~~~~~~~~~~~~~~~~~

+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|Fuel            |Original         |Fuel price €/GJ  |Source                 |Fuel price €/MWh       |Emission tCO2/GJ  |Fuel price including CO2 cost €/MWh|
+================+=================+=================+=======================+=======================+==================+===================================+
|hard_coal       |84.27 €/t SKE    |2.88             |  NEP2015a_, p.32      |10.3680                |0.0934            |20.7914                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|lignite         |1.50 €/MWh th    |0.42             |  NEP2015a_, p.32      |1.5120                 |0.1051            |13.2412                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|gas             |3.37 Cent/kWh    |9.36             |  NEP2015a_, p.32      |33.6960                |0.0559            |39.9344                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|oil             |128.00 $/bbl     |16.44            |  NEP2015a_, p.32      |59.1840                |0.0733            |67.3643                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|waste           |                 |1.86             |  IRENA2015_, p.125    |6.6960                 |0.0917            |16.9297                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|mixed_fuels     |                 |1.86             |  IRENA2015_, p.125    |6.6960                 |0.0917            |16.9297                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|biomass         |                 |7.58             |  PROGNOS2013_, p. 31  |27.2880                |0.0020            |27.5112                            |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+
|uranium         |                 |1.11             |  ISI2011_, p.94       |3.9960                 |0.0088            |4.9781                             |
+----------------+-----------------+-----------------+-----------------------+-----------------------+------------------+-----------------------------------+

with CO2 price = 31.00 €/t  NEP2015a_, p. 32
with 3.6 GJ ~ 1 MWh

Manipulations:
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

- Source: NEP2015b_, p.45
- Description: B1 2035/B2 2035
- Year: 2015
- Manipulations: Summed up federal state values. Combined heat and power sources smaller 10 MW run at the beginning and end of a year 4000 full-load-hours in total. (cf. FRAUNHOFER2014_, p.237 ff.)

+-------------+----------------+
|Source       | GW             |
+=============+================+
|gas          | 33.5           |
+-------------+----------------+
|hard_coal    | 11.0           |
+-------------+----------------+
|oil          |  0.5           |
+-------------+----------------+
|biomass      |  8.4           |
+-------------+----------------+
|lignite      |  9.1           |
+-------------+----------------+
|mixed_fuels  |  2.4           |
+-------------+----------------+
|wind_onshore | 88.8           |
+-------------+----------------+
|wind_offshore| 18.5           |
+-------------+----------------+
|solar        | 59.9           |
+-------------+----------------+
|hydro        |  4.2           |
+-------------+----------------+
|chp < 10 MW  |  8.2           |
+-------------+----------------+

Installed storage capacity aggregated by source in Germany

+-------------+----------------+
|Source       | GW             |
+=============+================+
|pumped_hydro | 12.7           |
+-------------+----------------+


Other countries
_______________

- Source: ENTSOE2014a_
- Description: 19:00pm values, Version 3 based on the EU longterm goals, See "Source". Original Data has been provided by ENTSO-E.
- Year: 2030 values assumed for  2035
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

- Source: ENTSOE2014b_
- Description:
- Year: 2030
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

.. _locations: https://github.com/znes/cFlEnS/blob/feature/open_eGo/open_eGo/modelpowerplants.geojson

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
.. _NEP2015a: http://www.netzentwicklungsplan.de/NEP_2025_1_Entwurf_Kap_1_bis_3.pdf
.. _IRENA2015: http://www.irena.org/DocumentDownloads/Publications/IRENA_REmap_Germany_report_2015.pdf
.. _ENTSOE2014a: https://www.entsoe.eu/Documents/SDC%20documents/SOAF/140602_SOAF%202014_dataset.zip
.. _ENTSOE2014b: https://www.entsoe.eu/major-projects/ten-year-network-development-plan/maps-and-data/Pages/default.aspx
.. _ENTSOE2014c: https://www.entsoe.eu/major-projects/ten-year-network-development-plan/tyndp-2014/Documents/TYNDP2014%20market%20modelling%20data.xlsx
.. _Bundesbank: https://www.bundesbank.de/Redaktion/DE/Downloads/Statistiken/Aussenwirtschaft/Devisen_Euro_Referenzkurs/stat_eurefd.pdf?__blob=publicationFile
.. _NEP2015b: https://www.netzentwicklungsplan.de/nep-file-download?file=media/2016-11/NEP_2025_1_Entwurf_Teil1.pdf
.. _FRAUNHOFER2014: https://ec.europa.eu/energy/sites/ener/files/documents/151221%20Mitteilung%20an%20KOM%20EED%20KWK%20Anlage%20Analyse.pdf
.. _EON2010: http://apps.eon.com/documents/EWK_Walchensee_2010_ger.pdf

Contact
=======

Martin Soethe (University of Flensburg): <martin.soethe(at)uni-flensburg.de>

Citation
========

Licence
=======

As mentioned above, there are currently some licensing issues due to the ENTSO-E data. The data will be published under a suitable license if these are cleared.
