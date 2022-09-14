wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/r-project.gpg
echo "deb [signed-by=/usr/share/keyrings/r-project.gpg] https://cloud.r-project.org/bin/linux/ubuntu jammy-cran40/" | sudo tee -a /etc/apt/sources.list.d/r-project.list
sudo apt update
sudo apt install --no-install-recommends r-base
sudo apt install libcurl4-openssl-dev
sudo apt install libxml2-dev
sudo apt-get -y install netcdf-bin
sudo apt-get install libnetcdf-dev
wget https://download1.rstudio.org/desktop/bionic/amd64/rstudio-2022.07.1-554-amd64.deb
sudo apt install -f ./rstudio-2022.07.1-554-amd64.deb

##### If you have the Error: Graphics API version mismatch in R
sudo rm -rf /usr/lib/R/site-library/ragg
sudo apt-get install -y libfreetype6-dev
sudo apt-get install -y libpng-dev
sudo apt-get install -y libtiff5-dev
sudo apt-get install -y libjpeg-dev
sudo R
BiocManager::install("ragg")
