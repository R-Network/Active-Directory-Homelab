# Drive Mapping

Network drives are deployed through Group Policy Preferences using the `Drive Maps` GPO.

## Department Drive Mappings

| Drive | Path                                              | Label       | Target Group        |
|---|---|---|---|
| `E:` | `\\VM-FILESERVER\SHARES\Departments\Engineering`   | Engineering | `Engineering-Users` |
| `F:` | `\\VM-FILESERVER\SHARES\Departments\Finance`       | Finance     | `Finance-Users`     |
| `H:` | `\\VM-FILESERVER\SHARES\Departments\HR`            | HR          | `HR-Users`          |
| `I:` | `\\VM-FILESERVER\SHARES\Departments\IT`            | IT          | `IT-Users`          |
| `M:` | `\\VM-FILESERVER\SHARES\Departments\Marketing`     | Marketing   | `Marketing-Users`   |
| `O:` | `\\VM-FILESERVER\SHARES\Departments\Operations`    | Operations  | `Operations-Users`  |
| `S:` | `\\VM-FILESERVER\SHARES\Departments\Sales`         | Sales       | `Sales-Users`       |

## Home and Public Drives

| Drive | Path                               | Label            |
|---|---|---|
| `Z:`  | `\\VM-FILESERVER\Users\%username%` | User Home Folder |
| `P:`  | `\\VM-FILESERVER\Public`           | Public           |