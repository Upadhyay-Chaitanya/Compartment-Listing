# Oracle Cloud Compartment Hierarchy Exporter

This script exports your Oracle Cloud Infrastructure (OCI) compartment hierarchy as a CSV file. It’s an ideal tool for gaining a clear, visual representation of all compartments (including deeply nested ones) in your tenancy.

---

## Features

- **Exports every compartment (including nested ones)**
- **Creates a hierarchical CSV** view with up to 5 levels (easily editable)
- **Straightforward config—just set your OCI profile name as needed**
- **Helpful for governance, audits, and documentation**

---

## Prerequisites

- Python 3.x installed
- [OCI Python SDK](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/pythonsdk.htm#Quickstart)  
  ```
  pip install oci
  ```
- An [OCI config file](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/sdkconfig.htm) (`~/.oci/config`) with an API key and correct profile

---

## Usage

1. **Set your OCI config profile:**  
   Edit the script and set `profile_name` to your desired profile  
   (`int03` by default)

2. **Run the script:**  
   ```sh
   python oci_compartment_hierarchy_export.py
   ```

3. **Find the output file:**  
   Output will be saved as  
   ```
   oci_compartments_hierarchy.csv
   ```
   (or similar, as indicated in the printout).

---

## Output

A CSV file showing your compartment structure, up to 5 levels deep:  
| Level 1  | Level 2        | Level 3     | Level 4  | Level 5  |
|----------|----------------|-------------|----------|----------|
| Root     | Subcomp 1      |             |          |          |
| Root     | Subcomp 2      | Sub-2a      | Sub-2a-1 |          |
| ...      | ...            | ...         | ...      | ...      |

(Empty cells mean fewer nested levels for that compartment branch.)

---

## Notes

- Increase or decrease the number of `Level` columns in both the script and output header as needed for your tenancy’s structure.
- Only active compartments are shown.
- Script uses the profile specified by `profile_name`.  
  Update as needed for your OCI environment.

---

## Example

```sh
python oci_compartment_hierarchy_export.py
```
Then open `oci_compartments_hierarchy.csv` with Excel or any spreadsheet tool.

---

## License

MIT License — see [LICENSE](./LICENSE) for details.

---

*Created and maintained by Upadhyay-Chaitanya*
