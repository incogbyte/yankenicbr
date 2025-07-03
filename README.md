# Brazilian ASN and IP Blocks Dataset

This repository provides a daily-updated, structured dataset of Brazilian Autonomous System Numbers (ASNs) and their associated IP address blocks.

The data is automatically fetched and parsed from the official file provided by [NIC.br](https://nic.br), the Brazilian Network Information Center. The goal of this project is to offer a clean, reliable, and easy-to-use version of this data for network analysis, security research, and other applications.

## Automation Process

A GitHub Action workflow runs automatically every 24 hours. The process is as follows:

1.  **Fetch Data:** The latest version file is downloaded.
2.  **Structure Data:** The raw information is transformed into structured formats.
3.  **Commit & Push:** The newly generated files are committed and pushed to this repository, ensuring the data is always current.

## Generated Files

The raw data is processed and made available in the `data/` directory in the following formats:

*   `data/all_data.json`
    A comprehensive JSON file containing an array of objects. Each object represents an organization and includes its ASN, name, document (CNPJ/CPF), and a list of its associated IP blocks.
    ```json
    [
      {
        "asn": 4230,
        "organization": "CLARO S.A.",
        "document": "40.432.544/0706-09",
        "ip_blocks": [
          "200.192.0.0/18",
          "200.210.0.0/16",
          "..."
        ]
      }
    ]
    ```

*   `data/asns.txt`
    A simple text file listing all unique Autonomous System Numbers (ASNs), sorted numerically, one per line.

*   `data/ips.txt`
    A simple text file listing all unique IP address blocks (in CIDR notation), sorted, one per line.
