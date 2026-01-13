# FC Flatmap Feature Mapping Store

A temporary repository to support mapping FC map features to CellML model components and variables

Here is a clean, professional update for your README that clearly outlines the contribution process and the strict data requirements.

---

# FC Flatmap Feature Mapping Store

A temporary repository to support mapping FC map features to CellML model components and variables.

## Contributing a New Map

To suggest a new map or update an existing one, please submit a **Pull Request**.

For your new map to function correctly with the `mapintegratedvuer`, your submission must adhere to the following file structure and formatting rules.

### 1. The Mapping File (`.xlsx`)

You must create an Excel file (saved as `.xlsx`) and place it in the `maps/` directory. This file requires a specific structure to be parsed correctly.

**Header Requirements:**
The first row must be a header row containing these three column names with these exact values:

1. `Name`
2. `Component`
3. `Flatmap ID`

Any other columns in the spreedsheet are ignored.

**Data Requirements:**

| Column | Description |
| --- | --- |
| **Name** | Must match the specific **variable name** in the CellML model. |
| **Component** | Must match the **component name** in the CellML model that the variable belongs to. |
| **Flatmap ID** | The specific ID of the visual feature on the flatmap that this component/variable maps to. |

### 2. The Index Entry (`mapping_index.json`)

You must register your new file in the `mapping_index.json` file located in the root of this repository.

* **Key:** The UUID of the flatmap.
* **Value:** The relative path to your `.xlsx` file inside the maps directory.

**Example Entry:**

```json
{
  "00000000-0000-0000-0000-000000000000": "maps/heart_model_mapping.xlsx"
}

```

### 3. Submit Pull Request

Once the Excel file is added and the index is updated, please open a Pull Request for review.
