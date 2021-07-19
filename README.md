This repository The source code for neutron cross section plotting website [xsplot.com](http://xsplot.com) which
allows neutron cross sections from TENDL 2019 to be plotted. Other libraries will be added soon.

This repository contains:
- A Python [Plotly Dash](https://plotly.com/dash/) based GUI 🐍
- A Dockerfile that provides the hosting enviroment 🐳

# Run locally

You can view the hosted version of this repositoy here [xsplot.com](http://xsplot.com). However you might want to host your own version locally.

To host your own local version of [xsplot.com](http://xsplot.com) you will need [Docker](https://www.docker.com/) installed and then can build and run the Dockerfile
with the following commands.

First clone the repositoy
```bash
git clone https://github.com/openmc-data-storage/xsplot.com.git
```

Then navigate into the repositoy folder
```bash
cd xsplot
```

Then build the docker image
```bash
docker build -t xsplot .
```

Then run the docker image
```bash
docker run --network host -t xsplot
```

The URL of your locally hosted version should appear in the terminal, copy and paste this URL into a web browser address bar.

# Maintenance

Pushing to the main branch of this repository triggers an automatic rebuild and
deployment of the new code using Google Cloud build at the [xsplot.com](http://xsplot.com)

The website makes use of a few other packages to process the nuclear data:
- [openmc_data_downloader](https://github.com/openmc-data-storage/openmc_data_downloader) to download processed h5 nuclear data files.
- [openmc_data_to_json](https://github.com/openmc-data-storage/openmc_data_to_json) to convert the h5 files (per isotope) into seperate reaction files.
- [nuclear_data_base_docker](https://github.com/openmc-data-storage/nuclear_data_base_docker) to provide a dockerfile containing all the required nuclear data with an index / loop up file containing every reaction available.
