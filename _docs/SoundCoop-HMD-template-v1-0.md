---
title: "SoundCoop hybrid millidecade (HMD) Specification Version 1.0"
keywords: [ioos, metadata, netCDF, 1.0]
tags: [ioos, metadata, netCDF, 1.0]
toc: false
#permalink: index.html
summary: This is version 1.0 of the SoundCoop hybrid millidecade (HMD) netCDF specification. 
---

## Revision History


| Version | Description                                                                                    | Date       |
|:--------|:-----------------------------------------------------------------------------------------------|:-----------|
| **1.0** | **SoundCoop hybrid millidecade (HMD) Version** <br>[Initial version](./SoundCoop-HMD-template-v1-0.html) | 2025-05-20 |

## Notes/Caveats

1. The SoundCoop hybrid millidecade (HMD) Specification is a compound profile that builds off of the [**NOAA NCEI NetCDF Templates v2.0**](https://www.ncei.noaa.gov/data/oceans/ncei/formats/netcdf/v2.0/index.html), meaning the full IOOS Metadata Profile is a combination of the NCEI Templates plus IOOS-specific guidance included in this document, such as:
* attributes that are passive acoustic specific (i.e. additions to the NCEI Templates)
* attributes where variations exist between the passive acoustic community guidance and the NCEI Templates (e.g. **`platform_vocabulary`**, where NCEI recommendations are specifically disallowed)
* attributes with a different role in the NCEI Templates; for example, the attribute **`_FillValue`** is **required** by the NCEI Template; however, in the IOOS Profile it is listed as **recommended** only;  conversely the opposite is possible as well
* attributes with otherwise modified or further qualified meanings/definitions

1. The NCEI Templates in turn build off of the ACDD and CF conventions.  Some attributes in the IOOS Profile originate from ACDD and CF (consult the `Convention` field in the table to determine the origin of each attribute).  Links to each are below:
* [NOAA NCEI NetCDF Templates 2.0](https://www.ncei.noaa.gov/data/oceans/ncei/formats/netcdf/v2.0/index.html)
* [Attribute Convention for Data Discovery 1.3](http://wiki.esipfed.org/index.php/Attribute_Convention_for_Data_Discovery_1-3)
* [Climate and Forecast Conventions (CF) 1.10](http://cfconventions.org/Data/cf-conventions/cf-conventions-1.10/cf-conventions.html)

1. In the SoundCoop hybrid millidecade (HMD) Specification doesn't define **required** or **recommended** attributes as it is an attempt to synthesize existing standards into a specific implementation for HMD.

## Gold Standard Example Datasets
* [Example dataset](https://storage.googleapis.com/noaa-passive-bioacoustic/ioos/products/sound_level_metrics/esons/esons_sc_m37_20210314-20210426_hmd/data/ESONS.SC.M37_437221.1.80000_20210314_DAILY_MILLIDEC_MinRes.nc)
* [Example in IOOS "ERDDAP Gold Standard" GitHub Repository]()

## SoundCoop hybrid millidecade (HMD) Specification Attributes

### Global Attributes

| attribute | description | example
|-----------|-------------|--------
| `CalibrationDate` | | 1970-01-01 00:00:00
| `CalibrationFrequency_Hz` | | 0.0
| `CalibrationSensitivity_dB_re_1VperRefPress` | | 0.0
| `PreampFixedGain_dB` | | 0.0
| `SamplingRate` | | 80000
| `acknowledgement` | | These products support the Passive Acoustic Monitoring National Cyberinfrastructure (SoundCoop) project funded by the NOAA Integrated Ocean Observatory System, Bureau of Ocean Energy Management, U.S. Navy Living Marine Resources, and Office of Naval Research.
| `citation` | | Cite as: University of South Carolina Beaufort and IOOS SECOORA. 2023. Hybrid Millidecade Spectra at 1 Minute Resolution Recorded at the Estuary Soundscape Observatory Network in the Southeast (ESONS) for IOOS SECOORA. NOAA National Centers for Environmental Information. https://doi.org/10.25921/0xbb-xx76. [access date]
| `comment` | | Data quality: Unusable 2021-03-14T00:00:00 to 2021-04-26T23:59:59 for channel 1 from 0Hz to 50Hz; Data quality: Good 2021-03-14T00:00:00 to 2021-04-26T23:59:59 for channel 1 from 51Hz to 40000Hz
| `conventions` | | COARDS, CF-1.6, ACDD-1.3
| `creator_name` | | Eric Montie
| `creator_role` | | Principal Investigator
| `date_created` | | 2024-09-21
| `geospatial_bounds` | | POINT (32.195 -80.792)
| `history` | | Original hybrid millidecade spectra were produced by Eric Montie. NCEI created this single standards-compliant netCDF file from the MANTA outputs plus additional metadata from the deployment and overall project. Conversion was done using v.1.2.0 of the NCEI MANTA netCDF converter.
| `id` | | https://doi.org/10.25921/0xbb-xx76
| `infoUrl` | | https://ncei.noaa.gov
| `institution` | | University of South Carolina Beaufort
| `instrument` | | Loggerhead
| `keywords` | | GCMD:oceans, GCMD:ocean acoustics, GCMD:ambient noise, intensity, GCMD:marine environment monitoring, marine habitat, sound intensity level in water, soundscapes
| `keywords_vocabulary` | | GCMD: GCMD Keywords
| `license` | | CC0-1.0
| `naming_authority` | | NOAA National Centers for Environmental Information
| `product_version` | | v1
| `project` | | ESONS, SoundCoop
| `publisher_email` | | pad.info@noaa.gov
| `publisher_name` | |  NOAA National Centers for Environmental Information
| `publisher_type` | | institution
| `publisher_url` | | https://www.ncei.noaa.gov/products/passive-acoustic-data
| `reference` | | Original audio recordings are available open-access: https://www.ncei.noaa.gov/maps/passive-acoustic-data/. Computation of single-sided mean-square sound pressure spectral density with 1 Hz resolution followed ISO 18405 3.1.3.13 (International Standard ISO 18405:2017(E), Underwater Acoustics – Terminology. Geneva: ISO). Hybrid millidecade band processing followed Martin et al. (2021; https://doi.org/10.1121/10.0003324)
| `source` | | Data analysis was performed using the Making Ambient Noise Trends Accessible (MANTA, https://bitbucket.org/CLO-BRP/manta-wiki/wiki/Home, see Miksis-Olds et al., 2021; Martin et al., 2021a,b) standalone software (v9.6.14) to produce hybrid millidecade spectra of sound levels from ocean audio recordings. To efficiently tackle large datasets, MANTA is designed around a parallel-processing Matlab package, Raven-X (Dugan et. al., 2014, 2016, and 2018) that uses ordinary multi-core computers to accelerate processing speeds. MANTA calculates the sound pressure spectral density (PSD) levels in units of 1 µPa^2/Hz using Welch's Method in Matlab. The Discrete Fourier Transform length is equal to the sample rate, a Hann window of equal length is applied to the data and 50% overlap is used. This results in PSD estimates of mean-square pressure amplitude (µPa^2) with a frequency resolution of 1 Hz and temporal resolution of 1 second. The 120 PSD estimates from each 1-minute segment were averaged, and the average spectrum for each minute was further processed to a hybrid millidecade (HMD) spectrum as dB re 1 µPa^2/Hz, as defined in Martin et al. (2021b). Hybrid millidecades are an efficient means of storing PSD spectra from high sample rate audio files using 1-Hz values up to 435 Hz, then millidecade wide PSD values up to one half of the sampling rate (Martin et al., 2021b). The MANTA outputs for each day are: (1) CSV of the 1 minute HMD results; (2) image of the daily long-term spectral average based on the 1 minute HMD results, (3) image of the daily spectral probability density with percentiles, and (4) NetCDF containing products 2 and 3 in addition to a deployment-level MANTA Metadata output file containing the associated frequency-dependent calibration data used to compute the calibrated spectrum levels.
| `standard_name_vocabulary` | | CF Standard Name Table v80
| `summary` | | To understand natural and anthropogenic sound in the ocean, and to compare underwater soundscapes globally, standard methods of analysis must be applied to passive acoustic monitoring (PAM) data. Methods that balance constrained volume and adequate resolution of acoustic spectra have recently been published (Martin et al., 2021a,b). A community effort supported by NOAA, BOEM, U.S. Navy, and ONR was initiated to apply these methods to PAM datasets from around the world. This record represents the hybrid millidecade (HMD) spectra of sound levels derived from calibrated passive acoustic data. Daily HMD at 1 minute resolution were created using standalone MANTA software (v9.6.14). These data were recorded at May River M37 between March 14, 2021 and April 26, 2021.
| `time_coverage_duration` | | P1D
| `time_coverage_resolution` | | P60S
| `time_offset` | | -4 hours from UTC
| `title` | | Hybrid Millidecade Band Sound Pressure Levels Computed at 1 Minute Resolution from Oceanic Passive Acoustic Monitoring Recordings at M37

### Variable Attributes

#### analog_sensitivity

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Analog sensitivity re 1 V per reference pressure
| `units` | | | dB
| `coverage_content_type` | | | physicalMeasurement
| `comment` | | | Sensitivity values in dB measured by the manufacturer were linearly interpolated to the center frequencies of hybrid millidecade bands


```
 <xarray.DataArray 'analog_sensitivity' (cal_frequency: 3206)> Size: 26kB
[3206 values with dtype=float64]
Coordinates:
  * cal_frequency  (cal_frequency) float64 26kB 0.0 1.0 ... 2.556e+05 2.56e+05
Attributes:
    long_name:              Analog sensitivity re 1 V per reference pressure
    units:                  dB
    coverage_content_type:  physicalMeasurement
    comment:                Sensitivity values in dB measured by the manufact... 
```

#### cal_frequency

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Calibration frequency for hybrid millidecade spectral bands
| `units` | | | Hz


```
 <xarray.DataArray 'cal_frequency' (cal_frequency: 3206)> Size: 26kB
array([0.000000e+00, 1.000000e+00, 2.000000e+00, ..., 2.549764e+05,
       2.555642e+05, 2.560000e+05])
Coordinates:
  * cal_frequency  (cal_frequency) float64 26kB 0.0 1.0 ... 2.556e+05 2.56e+05
Attributes:
    long_name:  Calibration frequency for hybrid millidecade spectral bands
    units:      Hz 
```

#### effort

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Duration of input data available for each 1-minute bin
| `coverage_content_type` | | | qualityInformation


```
 <xarray.DataArray 'effort' (time: 48)> Size: 384B
[48 values with dtype=timedelta64[ns]]
Coordinates:
  * time     (time) datetime64[ns] 384B 2021-03-14T00:01:00 ... 2021-03-14T23...
Attributes:
    long_name:              Duration of input data available for each 1-minut...
    coverage_content_type:  qualityInformation 
```

#### frequency

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `actual_range` | | | [1.e-01 4.e+04]
| `long_name` | | | Center frequency of hybrid millidecade spectral bands
| `standard_name` | | | sound_frequency
| `units` | | | Hz
| `coverage_content_type` | | | coordinate


```
 <xarray.DataArray 'frequency' (frequency: 2400)> Size: 19kB
array([1.00000e-01, 1.00000e+00, 2.00000e+00, ..., 3.98566e+04, 3.99485e+04,
       4.00000e+04])
Coordinates:
  * frequency  (frequency) float64 19kB 0.1 1.0 2.0 ... 3.995e+04 4e+04
Attributes:
    actual_range:           [1.e-01 4.e+04]
    long_name:              Center frequency of hybrid millidecade spectral b...
    standard_name:          sound_frequency
    units:                  Hz
    coverage_content_type:  coordinate 
```

#### preamp_gain

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Preamp gain
| `units` | | | dB


```
 <xarray.DataArray 'preamp_gain' (cal_frequency: 3206)> Size: 26kB
[3206 values with dtype=int64]
Coordinates:
  * cal_frequency  (cal_frequency) float64 26kB 0.0 1.0 ... 2.556e+05 2.56e+05
Attributes:
    long_name:  Preamp gain
    units:      dB 
```

#### psd

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Single-sided mean-square sound pressure spectral density re 1 micropascal^2/Hz
| `standard_name` | | | sound_intensity_in_water
| `units` | | | dB
| `comment` | | | Computation of single-sided mean-square sound pressure spectral density followed ISO 18405 3.1.3.13.
| `coverage_content_type` | | | physicalMeasurement


```
 <xarray.DataArray 'psd' (time: 48, frequency: 2400)> Size: 922kB
[115200 values with dtype=float64]
Coordinates:
  * time       (time) datetime64[ns] 384B 2021-03-14T00:01:00 ... 2021-03-14T...
  * frequency  (frequency) float64 19kB 0.1 1.0 2.0 ... 3.995e+04 4e+04
Attributes:
    long_name:              Single-sided mean-square sound pressure spectral ...
    standard_name:          sound_intensity_in_water
    units:                  dB
    comment:                Computation of single-sided mean-square sound pre...
    coverage_content_type:  physicalMeasurement 
```

#### quality_flag

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Data quality flag
| `standard_name` | | | quality_flag
| `comment` | | | 1 = Good, 2 = Not evaluated/Unknown, 3 =  Compromised/Questionable , 4 = Unusable / Bad
| `coverage_content_type` | | | qualityInformation


```
 <xarray.DataArray 'quality_flag' (time: 48, frequency: 2400)> Size: 115kB
[115200 values with dtype=int8]
Coordinates:
  * time       (time) datetime64[ns] 384B 2021-03-14T00:01:00 ... 2021-03-14T...
  * frequency  (frequency) float64 19kB 0.1 1.0 2.0 ... 3.995e+04 4e+04
Attributes:
    long_name:              Data quality flag
    standard_name:          quality_flag
    comment:                1 = Good, 2 = Not evaluated/Unknown, 3 =  Comprom...
    coverage_content_type:  qualityInformation 
```

#### recorder_gain

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Recorder gain
| `units` | | | dB


```
 <xarray.DataArray 'recorder_gain' (cal_frequency: 3206)> Size: 26kB
[3206 values with dtype=int64]
Coordinates:
  * cal_frequency  (cal_frequency) float64 26kB 0.0 1.0 ... 2.556e+05 2.56e+05
Attributes:
    long_name:  Recorder gain
    units:      dB 
```

#### sensor_sensitivity

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `long_name` | | | Sensor sensitivity re 1 V per reference pressure
| `units` | | | dB
| `coverage_content_type` | | | physicalMeasurement
| `comment` | | | Sensitivity values in dB measured by the manufacturer were linearly interpolated to the center frequencies of HMD bands.


```
 <xarray.DataArray 'sensor_sensitivity' (cal_frequency: 3206)> Size: 26kB
[3206 values with dtype=float64]
Coordinates:
  * cal_frequency  (cal_frequency) float64 26kB 0.0 1.0 ... 2.556e+05 2.56e+05
Attributes:
    long_name:              Sensor sensitivity re 1 V per reference pressure
    units:                  dB
    coverage_content_type:  physicalMeasurement
    comment:                Sensitivity values in dB measured by the manufact... 
```

#### time

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `actual_range` | | | [1615680060 1615762860]
| `long_name` | | | Time beginning each 1-minute temporal bin
| `standard_name` | | | time
| `coverage_content_type` | | | coordinate


```
 <xarray.DataArray 'time' (time: 48)> Size: 384B
array(['2021-03-14T00:01:00.000000000', '2021-03-14T01:00:00.000000000',
       '2021-03-14T01:01:00.000000000', '2021-03-14T02:00:00.000000000',
       '2021-03-14T02:01:00.000000000', '2021-03-14T03:00:00.000000000',
       '2021-03-14T03:01:00.000000000', '2021-03-14T04:00:00.000000000',
       '2021-03-14T04:01:00.000000000', '2021-03-14T05:00:00.000000000',
       '2021-03-14T05:01:00.000000000', '2021-03-14T06:00:00.000000000',
       '2021-03-14T06:01:00.000000000', '2021-03-14T07:00:00.000000000',
       '2021-03-14T07:01:00.000000000', '2021-03-14T08:00:00.000000000',
       '2021-03-14T08:01:00.000000000', '2021-03-14T09:00:00.000000000',
       '2021-03-14T09:01:00.000000000', '2021-03-14T10:00:00.000000000',
       '2021-03-14T10:01:00.000000000', '2021-03-14T11:00:00.000000000',
       '2021-03-14T11:01:00.000000000', '2021-03-14T11:02:00.000000000',
       '2021-03-14T12:00:00.000000000', '2021-03-14T12:01:00.000000000',
       '2021-03-14T13:00:00.000000000', '2021-03-14T13:01:00.000000000',
       '2021-03-14T14:00:00.000000000', '2021-03-14T14:01:00.000000000',
       '2021-03-14T15:00:00.000000000', '2021-03-14T15:01:00.000000000',
       '2021-03-14T16:00:00.000000000', '2021-03-14T16:01:00.000000000',
       '2021-03-14T17:00:00.000000000', '2021-03-14T17:01:00.000000000',
       '2021-03-14T18:00:00.000000000', '2021-03-14T18:01:00.000000000',
       '2021-03-14T19:00:00.000000000', '2021-03-14T19:01:00.000000000',
       '2021-03-14T20:00:00.000000000', '2021-03-14T20:01:00.000000000',
       '2021-03-14T21:00:00.000000000', '2021-03-14T21:01:00.000000000',
       '2021-03-14T22:00:00.000000000', '2021-03-14T22:01:00.000000000',
       '2021-03-14T23:00:00.000000000', '2021-03-14T23:01:00.000000000'],
      dtype='datetime64[ns]')
Coordinates:
  * time     (time) datetime64[ns] 384B 2021-03-14T00:01:00 ... 2021-03-14T23...
Attributes:
    actual_range:           [1615680060 1615762860]
    long_name:              Time beginning each 1-minute temporal bin
    standard_name:          time
    coverage_content_type:  coordinate 
```

#### timestamp

| attribute | disposition | description | example
|-----------|-------------|-------------|--------
| `actual_range` | | | ['2021-03-14T00:01:00', '2021-03-14T23:01:00']
| `long_name` | | | ISO timestamp beginning each 1-minute temporal bin
| `standard_name` | | | time


```
 <xarray.DataArray 'timestamp' (time: 48)> Size: 384B
[48 values with dtype=timedelta64[ns]]
Coordinates:
  * time     (time) datetime64[ns] 384B 2021-03-14T00:01:00 ... 2021-03-14T23...
Attributes:
    actual_range:   ['2021-03-14T00:01:00', '2021-03-14T23:01:00']
    long_name:      ISO timestamp beginning each 1-minute temporal bin
    standard_name:  time 
```

### Example Dataset:

#### Example File:

#### NCML:

```
xarray.Dataset {
dimensions:
	time = 48 ;
	frequency = 2400 ;
	cal_frequency = 3206 ;

variables:
	timedelta64[ns] timestamp(time) ;
		timestamp:actual_range = ['2021-03-14T00:01:00', '2021-03-14T23:01:00'] ;
		timestamp:long_name = ISO timestamp beginning each 1-minute temporal bin ;
		timestamp:standard_name = time ;
	timedelta64[ns] effort(time) ;
		effort:long_name = Duration of input data available for each 1-minute bin ;
		effort:coverage_content_type = qualityInformation ;
	float64 psd(time, frequency) ;
		psd:long_name = Single-sided mean-square sound pressure spectral density re 1 micropascal^2/Hz ;
		psd:standard_name = sound_intensity_in_water ;
		psd:units = dB ;
		psd:comment = Computation of single-sided mean-square sound pressure spectral density followed ISO 18405 3.1.3.13. ;
		psd:coverage_content_type = physicalMeasurement ;
	int8 quality_flag(time, frequency) ;
		quality_flag:long_name = Data quality flag ;
		quality_flag:standard_name = quality_flag ;
		quality_flag:comment = 1 = Good, 2 = Not evaluated/Unknown, 3 =  Compromised/Questionable , 4 = Unusable / Bad ;
		quality_flag:coverage_content_type = qualityInformation ;
	float64 analog_sensitivity(cal_frequency) ;
		analog_sensitivity:long_name = Analog sensitivity re 1 V per reference pressure ;
		analog_sensitivity:units = dB ;
		analog_sensitivity:coverage_content_type = physicalMeasurement ;
		analog_sensitivity:comment = Sensitivity values in dB measured by the manufacturer were linearly interpolated to the center frequencies of hybrid millidecade bands ;
	int64 preamp_gain(cal_frequency) ;
		preamp_gain:long_name = Preamp gain ;
		preamp_gain:units = dB ;
	int64 recorder_gain(cal_frequency) ;
		recorder_gain:long_name = Recorder gain ;
		recorder_gain:units = dB ;
	float64 sensor_sensitivity(cal_frequency) ;
		sensor_sensitivity:long_name = Sensor sensitivity re 1 V per reference pressure ;
		sensor_sensitivity:units = dB ;
		sensor_sensitivity:coverage_content_type = physicalMeasurement ;
		sensor_sensitivity:comment = Sensitivity values in dB measured by the manufacturer were linearly interpolated to the center frequencies of HMD bands. ;
	datetime64[ns] time(time) ;
		time:actual_range = [1615680060 1615762860] ;
		time:long_name = Time beginning each 1-minute temporal bin ;
		time:standard_name = time ;
		time:coverage_content_type = coordinate ;
	float64 frequency(frequency) ;
		frequency:actual_range = [1.e-01 4.e+04] ;
		frequency:long_name = Center frequency of hybrid millidecade spectral bands ;
		frequency:standard_name = sound_frequency ;
		frequency:units = Hz ;
		frequency:coverage_content_type = coordinate ;
	float64 cal_frequency(cal_frequency) ;
		cal_frequency:long_name = Calibration frequency for hybrid millidecade spectral bands ;
		cal_frequency:units = Hz ;

// global attributes:
	:acknowledgement = These products support the Passive Acoustic Monitoring National Cyberinfrastructure (SoundCoop) project funded by the NOAA Integrated Ocean Observatory System, Bureau of Ocean Energy Management, U.S. Navy Living Marine Resources, and Office of Naval Research. ;
	:citation = Cite as: University of South Carolina Beaufort and IOOS SECOORA. 2023. Hybrid Millidecade Spectra at 1 Minute Resolution Recorded at the Estuary Soundscape Observatory Network in the Southeast (ESONS) for IOOS SECOORA. NOAA National Centers for Environmental Information. https://doi.org/10.25921/0xbb-xx76. [access date] ;
	:comment = Data quality: Unusable 2021-03-14T00:00:00 to 2021-04-26T23:59:59 for channel 1 from 0Hz to 50Hz; Data quality: Good 2021-03-14T00:00:00 to 2021-04-26T23:59:59 for channel 1 from 51Hz to 40000Hz ;
	:conventions = COARDS, CF-1.6, ACDD-1.3 ;
	:creator_name = Eric Montie ;
	:creator_role = Principal Investigator ;
	:date_created = 2024-09-21 ;
	:geospatial_bounds = POINT (32.195 -80.792) ;
	:history = Original hybrid millidecade spectra were produced by Eric Montie. NCEI created this single standards-compliant netCDF file from the MANTA outputs plus additional metadata from the deployment and overall project. Conversion was done using v.1.2.0 of the NCEI MANTA netCDF converter. ;
	:id = https://doi.org/10.25921/0xbb-xx76 ;
	:infoUrl = https://ncei.noaa.gov ;
	:institution = University of South Carolina Beaufort ;
	:instrument = Loggerhead ;
	:keywords = GCMD:oceans, GCMD:ocean acoustics, GCMD:ambient noise, intensity, GCMD:marine environment monitoring, marine habitat, sound intensity level in water, soundscapes ;
	:keywords_vocabulary = GCMD: GCMD Keywords ;
	:license = CC0-1.0 ;
	:naming_authority = NOAA National Centers for Environmental Information ;
	:product_version = v1 ;
	:project = ESONS, SoundCoop ;
	:publisher_email = pad.info@noaa.gov ;
	:publisher_name =  NOAA National Centers for Environmental Information ;
	:publisher_type = institution ;
	:publisher_url = https://www.ncei.noaa.gov/products/passive-acoustic-data ;
	:reference = Original audio recordings are available open-access: https://www.ncei.noaa.gov/maps/passive-acoustic-data/. Computation of single-sided mean-square sound pressure spectral density with 1 Hz resolution followed ISO 18405 3.1.3.13 (International Standard ISO 18405:2017(E), Underwater Acoustics – Terminology. Geneva: ISO). Hybrid millidecade band processing followed Martin et al. (2021; https://doi.org/10.1121/10.0003324) ;
	:source = Data analysis was performed using the Making Ambient Noise Trends Accessible (MANTA, https://bitbucket.org/CLO-BRP/manta-wiki/wiki/Home, see Miksis-Olds et al., 2021; Martin et al., 2021a,b) standalone software (v9.6.14) to produce hybrid millidecade spectra of sound levels from ocean audio recordings. To efficiently tackle large datasets, MANTA is designed around a parallel-processing Matlab package, Raven-X (Dugan et. al., 2014, 2016, and 2018) that uses ordinary multi-core computers to accelerate processing speeds. MANTA calculates the sound pressure spectral density (PSD) levels in units of 1 µPa^2/Hz using Welch's Method in Matlab. The Discrete Fourier Transform length is equal to the sample rate, a Hann window of equal length is applied to the data and 50% overlap is used. This results in PSD estimates of mean-square pressure amplitude (µPa^2) with a frequency resolution of 1 Hz and temporal resolution of 1 second. The 120 PSD estimates from each 1-minute segment were averaged, and the average spectrum for each minute was further processed to a hybrid millidecade (HMD) spectrum as dB re 1 µPa^2/Hz, as defined in Martin et al. (2021b). Hybrid millidecades are an efficient means of storing PSD spectra from high sample rate audio files using 1-Hz values up to 435 Hz, then millidecade wide PSD values up to one half of the sampling rate (Martin et al., 2021b). The MANTA outputs for each day are: (1) CSV of the 1 minute HMD results; (2) image of the daily long-term spectral average based on the 1 minute HMD results, (3) image of the daily spectral probability density with percentiles, and (4) NetCDF containing products 2 and 3 in addition to a deployment-level MANTA Metadata output file containing the associated frequency-dependent calibration data used to compute the calibrated spectrum levels. ;
	:standard_name_vocabulary = CF Standard Name Table v80 ;
	:summary = To understand natural and anthropogenic sound in the ocean, and to compare underwater soundscapes globally, standard methods of analysis must be applied to passive acoustic monitoring (PAM) data. Methods that balance constrained volume and adequate resolution of acoustic spectra have recently been published (Martin et al., 2021a,b). A community effort supported by NOAA, BOEM, U.S. Navy, and ONR was initiated to apply these methods to PAM datasets from around the world. This record represents the hybrid millidecade (HMD) spectra of sound levels derived from calibrated passive acoustic data. Daily HMD at 1 minute resolution were created using standalone MANTA software (v9.6.14). These data were recorded at May River M37 between March 14, 2021 and April 26, 2021. ;
	:time_coverage_duration = P1D ;
	:time_coverage_resolution = P60S ;
	:time_offset = -4 hours from UTC ;
	:title = Hybrid Millidecade Band Sound Pressure Levels Computed at 1 Minute Resolution from Oceanic Passive Acoustic Monitoring Recordings at M37 ;
	:PreampFixedGain_dB = 0.0 ;
	:SamplingRate = 80000 ;
	:CalibrationFrequency_Hz = 0.0 ;
	:CalibrationSensitivity_dB_re_1VperRefPress = 0.0 ;
	:CalibrationDate = 1970-01-01 00:00:00 ;
}
```
