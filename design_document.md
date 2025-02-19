# Design guidelines for Reimplementation of Expertiza

This document outlines the common design features to be followed when developing views in the Expertiza environment.

## Text

* General font name: ```verdana,arial,helvetica,sans-serif```

* Headings/ Main title of page should be given in ```<h2>Title</h2>``` tag

* Capitalization:
    - Use camel case for headings.
    - Other text should have only the first letter of the first word capitalized, with all subsequent words in lowercase.

* Font sizes & line heights:
   - Standard text:
        - Font size: 13px
        - Line height: 30px
   - Subheadings:
        - Font size: 1.2em
        - Line height: 18px 
   - Table data:
        - Font size: 15px
        - Line height: 1.428em 

* Color
	- Menu bar - #FFFFFF; //for menubar with red background
	- Other titles/ text - #333; 
	- Text on red buttons - #fff;


## Tables

The **Table component** is prebuilt and must be used for all table-related functionalities. The component is located in:  
**`src/components/Table/Table.tsx`**

### Table usage
| **Requirement**        | **Implementation** |
|----------------------|------------------|
| **Component**       | Use **`Table.tsx`** (Do not create new table components) |
| **Styling**         | Bootstrap: `table table-striped` |
| **Global filter**   | **Disabled** |
| **Column filter**   | **Disabled** |
| **Pagination**      | Enabled only if **items ≥ 10** |
| **Sorting**        | Built-in with sorting indicators (`🔼` / `🔽`) |
| **Row selection**   | Available if `onSelectionChange` is provided |
| **Column visibility** | Configurable via `columnVisibility` prop |

### Example usage

```tsx
import Table from "src/components/Table/Table";

const columns = [
  { accessorKey: "name", header: "Student Name" },
  { accessorKey: "email", header: "Email Address" },
];

const data = [
  { name: "John Doe", email: "john@example.com" },
  { name: "Jane Smith", email: "jane@example.com" },
];

export default function ExampleTable() {
  return (
    <Table
      data={data}
      columns={columns}
      showGlobalFilter={false}
      showColumnFilter={false}
      showPagination={data.length >= 10}
    />
  );
}
```


---



## Icon library

Icons are available in four sizes: 16, 24, 32, and 48. However, it is possible that not all icons are available in every size. Edit the size number as needed; everything else will remain the same.
**Sr. No.** | **Element name** | **Image** | **Guide**	
|---|---|---|---|
|  1 |  Add assignment | ![Add assignment](public/assets/icons/add-assignment-24.png)  | To add 'add assignment' icon, use path **```/public/assets/icons/add-assignment-24.png```** |
|  2 |  Add teaching assistant | ![Add TA](public/assets/icons/add-ta-24.png)  | To add 'add TA' icon, use path **```public/assets/icons/add-ta-24.png```** |
|  3 |  Add private | ![Add private](public/assets/icons/add-private-24.png)  | To add 'add private' icon, use path **```public/assets/icons/add-private-24.png```** |
|  4 |  Add public | ![Add public](public/assets/icons/add-public-24.png)  | To add 'add public' icon, use path **```public/assets/icons/add-public-24.png```** |
|  5 |  Add signup sheet | ![Add signup sheet](public/assets/icons/add-signup-sheet-24.png)  | To add 'add signup sheet' icon, use path **```public/assets/icons/add-signup-sheet-24.png```** |
|  6 |  Assign course | ![Assign course](public/assets/icons/assign-course-blue-24.png)  | To add 'Assign course' icon, use path **```public/assets/icons/assign-course-blue-24.png```** |
|  7 |  Assign survey | ![Assign survey](public/assets/icons/assign-survey-24.png)  | To add 'Assign survey' icon, use path **```public/assets/icons/assign-survey-24.png```** |
|  8 |  Check | ![Check](public/assets/icons/Check-icon.png) | To add 'Check' icon, use path **```public/assets/icons/Check-icon.png```** |
|  9 | Copy | ![Copy](public/assets/icons/Copy-icon-24.png)  | To add 'Copy' icon, use path **```public/assets/icons/Copy-icon-24.png```** |
|  10 |  Create team | ![Create team](public/assets/icons/create-teams-24.png)  | To add 'Create team' icon, use path **```public/assets/icons/create-teams-24.png```** |
|  11 |  Delete | ![Delete](public/assets/icons/delete-icon-24.png)  | To add 'Delete' icon, use path **```public/assets/icons/delete-icon-24.png```** |
|  12 |  (General) Edit | ![Edit](public/assets/icons/edit-icon-24.png)  | To add 'Edit' icon, use path **```public/assets/icons/edit-icon-24.png```** |
|  13 |  Edit signup sheet | ![Edit Signup sheet](public/assets/icons/edit-signup-sheet-24.png)  | To add 'Edit signup sheet' icon, use path **```public/assets/icons/edit-signup-sheet-24.png```** |
|  14 |  Info | ![Info](public/assets/icons/info.png) | To add 'Info' icon, use path **```public/assets/icons/info.png```** |
|  15 | List all | ![List All](public/assets/icons/image8.png)  | To add 'List all' icon, add class as "glyphicon glyphicon-list-alt" |
|  16 |  List submissions | ![List Submissions](public/assets/icons/List-submisstions-24.png)  | To add 'List submissions' icon, use path **```public/assets/icons/List-submissions-24.png```** |
|  17 |  Make public from private | ![Make public from private](public/assets/icons/lock-off-disabled-icon-24.png)  | To add 'Make public from private' icon,  use path **```public/assets/icons/lock-off-disabled-icon-24.png```**   |
|  18 |  Private | ![Private](public/assets/icons/lock-disabled-icon-24.png)  | To add 'Private' icon,  use path **```public/assets/icons/lock-disabled-icon-24.png```**   |
|  19 |  Remove from course | ![Remove from course](public/assets/icons/remove-from-course-24.png)  | To add 'Remove from course' icon,  use path **```public/assets/icons/remove-from-course-24.png```**   |
|  20 |  Run bidding assignment | ![Run bidding assignment](public/assets/icons/run-lottery.png)  | To add 'Run bidding assignment' icon,  use path **```public/assets/icons/run-lottery.png```**   |
|  21 | Signup | ![Signup](public/assets/icons/signup.png) | To add 'Signup' icon, use path **```public/assets/icons/signup.png```** |
|  22 |  Search | ![Search](public/assets/icons/view-publish-rights-24.png)  | To add 'Search' icon,  use path **```public/assets/icons/view-publish-rights-24.png```**   |
|  23 | Uncheck | ![Uncheck](public/assets/icons/Uncheck-icon.png) | To add 'Uncheck' icon, use path **```public/assets/icons/Uncheck-icon.png```** |
|  24 | View delayed mailer | ![View delayed mailer](public/assets/icons/view-delayed-mailer.png) | To add 'View delayed mailer' icon, use path **```public/assets/icons/view-delayed-mailer.png```** |
|  25 |  View report | ![View report](public/assets/icons/view-review-report-24.png)  | To add 'View report' icon,  use path **```public/assets/icons/view-review-report-24.png```**   |
|  26 |  View scores | ![View scores](public/assets/icons/view-scores-24.png)  | To add "View score" icon,  use path **```public/assets/icons/view-scores-24.png```**   |
|  27 |  View suggestions | ![View suggestions](public/assets/icons/view-suggestion-24.png)  | To add "View suggestions" icon,  use path **```public/assets/icons/view-suggestion-24.png```**   |
|  28 |  View survey | ![View survey](public/assets/icons/view-survey-24.png)  | To add "View survey" icon,  use path **```public/assets/icons/view-survey-24.png```**   |
---

## Buttons 

The default color for buttons is red 

we recommend using the `Button` class from `react-bootstrap` to ensure a consistent and unified appearance.

**Sr. No.** | **Element name** | **Image** | **Guide** | **Class** | **Variant** |
|---|---|---|---|---|---|
|  1 |  Button - Default style | *to be added*  | Default button | `btn btn-md` | `outline-secondary` |
|  2 |  Button - Success style | *to be added*  | For accepting. | `btn btn-md` | `success` |
|  3 |  Button - Danger style | *to be added*  | For rejecting. | `btn btn-md` | `danger` |
|  4 |  Button - New style | *to be added*  | For create buttons alone. | `btn pull-right new-button btn-md` | `primary` |

### ✅ Example usage

#### **Default button**
```tsx
import { Button } from "react-bootstrap";

<Button className="btn btn-default btn-md">Click Me</Button>
```


---
## Notifications

All notifications must follow **Bootstrap’s alert styling** and use the **predefined classes** to ensure consistency across the UI.

### 📌 Notification styles
| **Sr. No.** | **Element name** | **Guide** | **Class** |
|---|---|---|---|
|  1 |  Success | Display success messages | ```flash_note alert alert-success``` |
|  2 |  Error | Display error messages | ```flash_note alert alert-danger``` |
|  3 |  Info | Display informational messages | ```flash_note alert alert-info``` |
|  4 |  Warn | Display warning messages | ```flash_note alert alert-warning``` |

---

### ✅ Example usage

#### **Success notification**
```tsx
import { Alert } from "react-bootstrap";

<Alert className="flash_note alert alert-success">
  Operation completed successfully!
</Alert>
```



---

## Forms

The **Form component** is prebuilt and must be used for all Form-related functionalities. The component is located in:  
**`src/components/Form`**

| **Requirement**          | **Implementation**                                             |
|--------------------------|----------------------------------------------------------------|
| **Component**            | Use **prebuilt form components** (Do not create new form elements) |
| **Styling**              | Bootstrap: `form-control`                                      |
| **Validation**           | Built-in via **Formik**                                        |
| **Tooltips**             | Use `ToolTip` from `src/components/ToolTip.tsx`                |
| **Date picker**          | Uses `react-datepicker`, preconfigured                         |
| **Checkbox & radio groups** | Prebuilt in `FormCheckboxGroup.tsx` and `FormRadioGroup.tsx`    |
| **Dropdowns**            | Use `FormSelect.tsx` (prebuilt)                                |
| **Range sliders**        | Use `FormRange.tsx`                                            |




## Dropdowns and toggling dropdowns

For dropdowns and toggling functionality, we recommend using the `Dropdown` class from `react-bootstrap` to ensure a consistent and unified appearance. 

The `react-bootstrap` library is already included in the `package.json` file, so you can directly utilize the provided dropdown styles.

## Pagination 

Disable pagination components when fewer than 10 items are displayed on the page.

Pagination Component is already included in the Repository under **```src\components\Table\Pagination.tsx```**. We recommend using this component to maintain consistency.
