## AWScli set up

Download and install the AWScli version appropriate for your computer.

https://aws.amazon.com/cli/


## Venv creation and setup

1) Make venv:   python –m venv workshop_venv

 

2) Activate venv

 

	2.a Bash style terminal: source workshop_venv/Scripts/activate  

	2.b Windows CMD: Change directories until you are inside the Scripts folder inside your venv folder. Then run “activate”

 

3) Update pip: python -m pip install --upgrade pip


## Libraries for the venv

### Automated: 

pip install –r requirements.txt

### Manual:

pip install awscli

pip install "importlib-metadata<5.0"

pip install netcdf4            (if you get problems, add the -- prefer-binary flag)

pip install xarray

pip install ipykernel   

pip install pyarrow

pip install polars


## AWS command examples

aws s3 **ls** --no-sign-request  --no-verify-ssl s3://era5-pds/


**Check contents of a folder in a bucket**

aws s3 **ls** --no-sign-request  --no-verify-ssl s3://era5-pds/2022/01/data/

**Copying a single file**

aws s3 **cp** --no-sign-request  --no-verify-ssl s3://era5-pds/2022/01/data/sea_surface_temperature.nc  *name_you_want_on_your_drive.nc*


**Copying the contents of a folder**

aws s3 **cp**  --no-sign-request --no-verify-ssl --recursive s3://era5-pds/2022/01/data/  *nameOfChosenFolder/*


**Copying selected files across different folders**


aws s3 cp  --no-sign-request --no-verify-ssl --recursive s3://era5-pds/2022/   nameOfChosenFolder/  **--exclude "\*" --include "\*temperature.nc"**

## A useful tutorial
Particularly, pay attention to how to slide an xarray by coordinates, so that you can focus on your area of interest (for example, you could cover only the coordinates for the UK).

https://spire.com/tutorial/spire-weather-tutorial-intro-to-processing-grib2-data-with-python/
