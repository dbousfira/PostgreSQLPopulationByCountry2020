# population-by-country-2020

<p align="center">
  <h3 align="center">Les pays en chiffre</h3>

  <p align="center">
    Vous avez récolté des informations basiques sur les pays et vous allez manipuler les données
</p>

<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)

<!-- ABOUT THE PROJECT -->
## About The Project

### Built With

* [PostgreSQL](http://postgresql.fr/)

<!-- GETTING STARTED -->
## Getting Started

Copy up and running follow these simple steps.

### Prerequisites

* [PostgreSQL](http://postgresql.fr/)

### Installation

1. Run SQL file

    ```sh
    psql -h <hostname> -U <username> -d <db> -f script.sql
    ```

    OR

    Copy/paste the content of the script file inside your PostgreSQL tool

<!-- USAGE EXAMPLES -->
## Usage

* créer une fonction SQL qui retourne le pays (sous format de TABLE) qui correspond au critère passé en paramètre. Ce paramètre est le nom du pays

    ```sql
    SELECT * FROM get_country_by_name('<country>');
    ```

* créer une procédure SQL qui insert un nouveau pays avec des données random (on précise uniquement le pays)

    ```sql
    CALL insert_data('<country>');

    SELECT * FROM country
    WHERE country = '<country>'
    ```

* configurer un trigger qui va mettre à jour la colonne de la table correspondant à la date de l'insertion

    ```sql
    CALL insert_data('<country>');

    SELECT * FROM country
    WHERE country = '<country>'
    ```

* réaliser une fonction ou procédure stoquée pour retourner les pays qui sont regroupés par 4 tranches (à definir) de densité de population

    ```sql
    SELECT * FROM get_country_by_quartile_density();
    ```
