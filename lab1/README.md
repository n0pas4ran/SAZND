{
  "cells": [
    {
      "cell_type": "raw",
      "metadata": {},
      "source": [
        "---\n",
        "title: \"pr1\"\n",
        "format: md\n",
        "editor: visual\n",
        "---"
      ],
      "id": "c33d51e0"
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## Running Code\n",
        "\n",
        "Getting kernel name\n",
        "\n",
        "\n",
        "```{bash}\n",
        "uname -a\n",
        "```\n",
        "\n",
        "\n",
        "Getting proc model name\n",
        "\n",
        "\n",
        "```{bash}\n",
        "cat /proc/cpuinfo | grep \"model name\" | tail -n 1\n",
        "```\n",
        "\n",
        "\n",
        "Check for last 30 operations of bash\n",
        "\n",
        "\n",
        "```{bash}\n",
        "cat ./.bash_history | tail -n 30\n",
        "\n",
        "```"
      ],
      "id": "f3cf1cb6"
    }
  ],
  "metadata": {
    "kernelspec": {
      "display_name": "Python 3",
      "language": "python",
      "name": "python3"
    }
  },
  "nbformat": 4,
  "nbformat_minor": 5
}