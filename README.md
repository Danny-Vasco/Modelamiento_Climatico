Modelamiento de Microclima con Downscaling de Datos CMIP6 aplicado a la provincia de Pichincha-Ecuador un caso de estudio.
Autor: Basado en código de usuario
Versión: 1.0
Fecha: Abril 2026
1. Introducción
El presente manual describe paso a paso un flujo de trabajo para generar mapas de temperatura microclimática a escala local (downscaling) utilizando datos climáticos globales CMIP6 (WorldClim 2.5 min), un Modelo Digital de Elevación (DEM), cobertura del suelo y correcciones por radiación solar. El objetivo es obtener escenarios futuros de temperatura (ej. 2050) bajo el escenario SSP2 4.5, integrando efectos topográficos y de uso de suelo.
El código está escrito en Python y emplea librerías geoespaciales como rasterio, rioxarray, geopandas, xarray y matplotlib.
2. Requisitos e instalación
2.1. Entorno Python
Se recomienda usar Python 3.10 o superior. Instalar las siguientes librerías:
pip install rasterio numpy matplotlib geopandas rioxarray xarray

2. Datos de entrada necesarios
•	Variables climáticas CMIP6 (ejemplo para SSP2 4.5, periodo 2021 2040):
o	wc2.1_2.5m_tmin_BCC-CSM2-MR_ssp245_2021-2040.tif
o	wc2.1_2.5m_tmax_BCC-CSM2-MR_ssp245_2021-2040.tif
•	DEM de la zona de estudio (ej. Cut_Dem.tif).
•	Cobertura del suelo (land cover) en formato ráster (ej. Land_cover.tif).
•	Shapefile del área de interés (ej. Pichincha.shp).

3. Consideraciones finales
•	Calibración: Los factores gamma, factor_rad, factor_lc deben ajustarse según datos observados locales.
•	Resolución espacial: El downscaling hereda la resolución del ráster de referencia (2.5 minutos ≈ 5 km). Para mayor detalle, usa DEM de alta resolución.
•	Escenarios futuros: El código usa SSP2 4.5 (trayectoria intermedia). Puedes cambiar a SSP1 2.6 o SSP5 8.5 descargando otros modelos.
•	Validación: Compara siempre con estaciones meteorológicas locales para verificar la corrección.
8. Referencias
•	WorldClim versión 2.1: https://worldclim.org
•	CMIP6: Eyring et al. (2016) Geoscientific Model Development
•	Lapse rate estándar: 6.5 °C/km (atmósfera estándar)
________________________________________
Nota final: Este manual es una guía didáctica. Para aplicaciones profesionales se recomienda revisar cada paso y validar los supuestos físicos con expertos en climatología.
