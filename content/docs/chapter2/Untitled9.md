---
date: 2021-12-01
title: My first blog post
type: book
---



{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Untitled9.ipynb",
      "provenance": [],
      "authorship_tag": "ABX9TyN7BV1q7V9C5uArQg3FTQk6",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/tsai-jiewen/N4EM/blob/main/content/docs/chapter2/Untitled9.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "qIS-q08auv5z"
      },
      "outputs": [],
      "source": [
        "%load_ext rpy2.ipython"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%%R\n",
        "install.packages('psych')"
      ],
      "metadata": {
        "id": "7A2SL0qExE1S"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import numpy as np\n",
        "import matplotlib.pyplot as plt\n",
        "\n",
        "x = np.linspace(0, 10, 1000)\n",
        "plt.plot(x, np.sin(x));\n",
        "\n",
        "plt.show()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 265
        },
        "id": "mfg8FB9n-U9u",
        "outputId": "bc94bc3e-dfd5-4673-8a09-bfb559524359"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\n",
            "text/plain": [
              "<Figure size 432x288 with 1 Axes>"
            ]
          },
          "metadata": {
            "needs_background": "light"
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "!pip3 install http://download.pytorch.org/whl/cu80/torch-0.3.0.post4-cp36-cp36m-linux_x86_64.whl\n",
        "!pip3 install torchvision"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "jmsEp3CM-8ab",
        "outputId": "53122d0a-ec6b-4d06-bb40-2dbd8e15912d"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "\u001b[31mERROR: torch-0.3.0.post4-cp36-cp36m-linux_x86_64.whl is not a supported wheel on this platform.\u001b[0m\n",
            "Requirement already satisfied: torchvision in /usr/local/lib/python3.7/dist-packages (0.11.1+cu111)\n",
            "Requirement already satisfied: pillow!=8.3.0,>=5.3.0 in /usr/local/lib/python3.7/dist-packages (from torchvision) (7.1.2)\n",
            "Requirement already satisfied: numpy in /usr/local/lib/python3.7/dist-packages (from torchvision) (1.19.5)\n",
            "Requirement already satisfied: torch==1.10.0 in /usr/local/lib/python3.7/dist-packages (from torchvision) (1.10.0+cu111)\n",
            "Requirement already satisfied: typing-extensions in /usr/local/lib/python3.7/dist-packages (from torch==1.10.0->torchvision) (3.10.0.2)\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "from sympy import Integral, sqrt, symbols, init_printing\n",
        "\n",
        "init_printing()\n",
        "\n",
        "x = symbols('x')\n",
        "\n",
        "Integral(sqrt(1 / x), x)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 60
        },
        "id": "t4ufdGss-dIk",
        "outputId": "b902657d-9a3d-4888-91a0-c9e2547a6e3d"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "image/png": "iVBORw0KGgoAAAANSUhEUgAAAF4AAAAhCAYAAABQphx6AAAABHNCSVQICAgIfAhkiAAABBlJREFUaIHt2FuIlVUUB/DfpMYUJT54oUIku/pQmqFFWE4lRZaVZQ/NQwRFERRSEJIVSWSG1YtBIVEMXaAQI5xu9mCUBV3owjxoEF00y+5miZWXpoe9z5yL5zvf5cwZx+n84fBd1trrv7511l577U0bwx4dGHWwnfg/oRMrsAO7sFKxP6ADt6B/mP6GHZ51oJNLC9iZjTsH0a8RjYn4Vwj2bbgm3n9bwNb9mDZ4rh3aGJ0inyGUCHgeO/EafsaR2J2Daxo253VwpCIt8OPj9W/8Fu8vLcBzLL4rMG7E4rAU+dHx+keTPJfhlSZtjCikBf6oeN3VJM9cvN2kjeGEycJa91JRA1kz/s+iBEI7ug97E+SL8Bg2CjOrH89ltD0J++P4ocSZ8fpJUQNpNX4wMv5CbGggvwfTI8c2nJrD9hVC8hTOvIKYGa8fFzUwFBl/idAJJeF2nIyxwgYrDxbiV7xTzLXCaDrjh6LGTxDazyS8hS/k3z2OxQXoFcpNCW9GW1fX6HegJ8oeymB/NBajT+jqtmBJtDMT3+PHFvCCdXHA0yl6p0UnazFdvl1ul+w1vjvqXl6Hcz82qT7aeDTqr85g+3DlQH6Kh4UY/IUn4/t1LeAdwIY4aFUDnbnRuW11ZHfj9Bx8XbIHfo0wEzvryHqinevj89L4/KL0WU45uPcqbyDhPOVjk2Ut4B3AR3Hg8hS9cfhHedEp4YU8ZLIHvlNYd9YkyCcL2fk1bo023xAyOQ2zo35vgnxTlC8YZN4qbI6D78qgu151FkyQv83rki3wC6JedwOdFcrZ+Z5wxJEFpUPBsxPkG6P8uGZ4B7Or6VWdBfM17maawVXYg1cb6FQu6DfIfq50kdApfZAgn4qfJB+BFOWtwu+qa1YjTBFOMkuZ0KN+/W2ELukZPwq/4PUGOt3Rl+3R3hMZ+TujflKbODPKkxKqKO8B2Kd+i5SEPtyMMXimAF+X9MCfH3VuSpDPF2ZDn1DuPhd2zadk4B8jfHO9RgHWRu4HBpm3Ckco16qLM45ZLhyGzcONeQllC/wqoW2bVEc2R5jaX+GY+G5RtPlyRh9K61rt4rlEOR4LW8A7gIkVROdkHHOWsKqvrnAgDVcKZalH6AD68WXFu0cqdDuwFe/WsTNDKI3bcUKNrNSdnZvBn+ui7h5h1q7Eh8J3bY2yKS3gHcBU5cBn7cU78APez8GzrIKn3u+bCt1Z8d0dNTZOjLw7EnydF8dl9WuxkL17hd3pWqG+bxHWl1bxIuzESh9/fI5xT+G+PEQ58KD8/hxymKMc+PEpupWYhZNa4lGov5+1yPZBw2yhTXo8Pl8rBH2vnNvdNvKhVNN34wxhc9IvLBBttBi9DlzcsvbwbTSBcUIPvVOopbVHrm200UYbbbTRRgr+A/wbW2KRnqk7AAAAAElFTkSuQmCC\n",
            "text/latex": "$\\displaystyle \\int \\sqrt{\\frac{1}{x}}\\, dx$",
            "text/plain": [
              "⌠           \n",
              "⎮     ___   \n",
              "⎮    ╱ 1    \n",
              "⎮   ╱  ─  dx\n",
              "⎮ ╲╱   x    \n",
              "⌡           "
            ]
          },
          "metadata": {},
          "execution_count": 28
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%%R\n",
        "library(tidyverse)\n",
        "library(psych)\n",
        "dat_loan <- read.table('loan.txt', header=T)"
      ],
      "metadata": {
        "id": "Gh-MDDAnu1Em"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "%%R\n",
        "des <- psych::describe(dat_loan)"
      ],
      "metadata": {
        "id": "0Eu7HDTfw1fa"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        ""
      ],
      "metadata": {
        "id": "wh2g4MVEyZNz"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "%%R\n",
        "c(1:10) |> sum()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "jIXboV8JvQHe",
        "outputId": "ba0974f5-89dd-4676-80e9-11b55ec613bf"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "[1] 55\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "%%R\n",
        "sessionInfo()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "WD29ywyZvfO2",
        "outputId": "6df37430-89ec-4437-f02e-a5aa3e32a337"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "R version 4.1.2 (2021-11-01)\n",
            "Platform: x86_64-pc-linux-gnu (64-bit)\n",
            "Running under: Ubuntu 18.04.5 LTS\n",
            "\n",
            "Matrix products: default\n",
            "BLAS:   /usr/lib/x86_64-linux-gnu/openblas/libblas.so.3\n",
            "LAPACK: /usr/lib/x86_64-linux-gnu/openblas/liblapack.so.3\n",
            "\n",
            "locale:\n",
            " [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C              \n",
            " [3] LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8    \n",
            " [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   \n",
            " [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                 \n",
            " [9] LC_ADDRESS=C               LC_TELEPHONE=C            \n",
            "[11] LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       \n",
            "\n",
            "attached base packages:\n",
            "[1] tools     stats     graphics  grDevices utils     datasets  methods  \n",
            "[8] base     \n",
            "\n",
            "other attached packages:\n",
            "[1] forcats_0.5.1   stringr_1.4.0   dplyr_1.0.7     purrr_0.3.4    \n",
            "[5] readr_2.1.1     tidyr_1.1.4     tibble_3.1.6    ggplot2_3.3.5  \n",
            "[9] tidyverse_1.3.1\n",
            "\n",
            "loaded via a namespace (and not attached):\n",
            " [1] Rcpp_1.0.7       cellranger_1.1.0 pillar_1.6.4     compiler_4.1.2  \n",
            " [5] dbplyr_2.1.1     jsonlite_1.7.2   lubridate_1.8.0  lifecycle_1.0.1 \n",
            " [9] gtable_0.3.0     pkgconfig_2.0.3  rlang_0.4.12     reprex_2.0.1    \n",
            "[13] cli_3.1.0        rstudioapi_0.13  DBI_1.1.2        haven_2.4.3     \n",
            "[17] xml2_1.3.3       withr_2.4.3      httr_1.4.2       fs_1.5.2        \n",
            "[21] generics_0.1.1   vctrs_0.3.8      hms_1.1.1        grid_4.1.2      \n",
            "[25] tidyselect_1.1.1 glue_1.6.0       R6_2.5.1         fansi_0.5.0     \n",
            "[29] readxl_1.3.1     tzdb_0.2.0       modelr_0.1.8     magrittr_2.0.1  \n",
            "[33] backports_1.4.1  scales_1.1.1     ellipsis_0.3.2   rvest_1.0.2     \n",
            "[37] assertthat_0.2.1 colorspace_2.0-2 utf8_1.2.2       stringi_1.7.6   \n",
            "[41] munsell_0.5.0    broom_0.7.10     crayon_1.4.2    \n"
          ]
        }
      ]
    }
  ]
}

