
<a id="readme-top"></a>

[![Unlicense License][license-shield]][license-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/RWS-CFNS/MastLocatieVerwerker">
    <img src="images/MastVerwerkerLogo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">MastLocatieVerwerker</h3>

  <p align="center">
    Retrieves the location of the connected towers from OpenCellID
    <br />
    <a href="https://github.com/RWS-CFNS/MastLocatieVerwerker"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/RWS-CFNS/MastLocatieVerwerker">View Demo</a>
    &middot;
    <a href="https://github.com/RWS-CFNS/MastLocatieVerwerker/issues/new?labels=bug&template=bug-report---.md">Report Bug</a>
    &middot;
    <a href="https://github.com/RWS-CFNS/MastLocatieVerwerker/issues/new?labels=enhancement&template=feature-request---.md">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## System Architecture Overview
![Integration with other CFNS systems](images/integrationMastLocatieVerwerker.png)

This application automates the process of retrieving and updating cell tower locations using the OpenCellID API and a PostgreSQL database. It scans the database for records with missing latitude and longitude values, extracts the necessary network identifiers (MCC, MNC, LAC/TAC, and Cell ID), and queries OpenCellID for their precise geolocation. Once retrieved, the coordinates are stored back in the database, ensuring accurate mapping of network infrastructure.
Key Features:

* Database Connectivity: Seamlessly connects to a PostgreSQL database to identify and update missing cell tower locations.
* API Integration: Uses the OpenCellID API to fetch precise geolocation data based on network identifiers.
* Automated Data Processing: Ensures accuracy by verifying API responses before updating records, improving the quality of network analysis.

This app is particularly useful for telecom companies, network analysts, and researchers looking to enhance cellular coverage data and infrastructure mapping.

Use the `BLANK_README.md` to get started.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

This section lists any major frameworks/libraries used while developing this tool.

[![Eclipse][Eclipse.org]][Eclipse-url]
[![Maven][Maven.org]][Maven-url]
[![Python][Python.org]][Python-url]
[![OpencellID][OpencellID.org]][OpencellID-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Getting Started

### Prerequisites

Ensure you have Python 3 installed on your system.

### Installation

1. Download the latest release from the [Releases Page](https://github.com/RWS-CFNS/MastLocatieVerwerker/releases) and extract the ZIP file.
2. Configure database and API parameters by updating the script with your credentials:
   ```python
   db_host = "your_postgres_host"
   db_name = "your_database_name"
   db_user = "your_database_user"
   db_password = "your_database_password"
   db_port = "5432"
   api_key = "your_opencellid_api_key"
   ```
3. Run the script manually to test:
   ```sh
   python3 script.py
   ```

## Usage

The script queries a PostgreSQL database for missing latitude and longitude values, retrieves data from the OpenCellID API, and updates the database accordingly.

For best results, schedule the script to run automatically using a cron job.

*For more details, refer to the API documentation at **[OpenCellID](https://opencellid.org)*


<!-- LICENSE -->
## License

Distributed under the Unlicense License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


[license-shield]: https://img.shields.io/github/license/RWS-CFNS/MastLocatieVerwerker.svg?style=for-the-badge
[license-url]: https://github.com/RWS-CFNS/MastLocatieVerwerker/blob/master/LICENSE.txt

[Eclipse.org]: https://img.shields.io/badge/Eclipse-7E48BD?style=for-the-badge&logo=eclipse&logoColor=white
[Eclipse-url]: https://Eclipse.org/
[Python.org]: https://img.shields.io/badge/Python-1985A1?style=for-the-badge&logo=python&logoColor=white
[Python-url]: https://python.org/
[Opencellid.org]: https://img.shields.io/badge/Opencellid-F09728?style=for-the-badge
[Opencellid-url]: https://Opencellid.org/
[Maven.org]: https://img.shields.io/badge/Maven-6A005C?style=for-the-badge&logo=apachemaven&logoColor=white
[Maven-url]: https://maven.apache.org/
