# Sample Data Folder

This folder contains sample input data and expected outputs for the **Backup Verification Simulator** project.

The actual application works with SQLite `.db` backup files generated inside:

```text
database/backup/
```

For submission and demo purposes, this folder explains the type of input used and the expected output generated after validation.

## Input Files Used

### 1. Healthy Backup Input

Example file:

```text
database/backup/backup_YYYYMMDD_HHMMSS.db
```

Expected database tables:

- `users`
- `transactions`

Expected sample data:

- `users` table contains 100 user records.
- `transactions` table contains 500 transaction records.
- Transaction amounts are valid positive values.
- No required table is missing.

### 2. Corrupted Backup Input

The simulator can intentionally create corrupted backups for testing.

Possible corruption examples:

- `users` table is dropped.
- `transactions` table is empty.
- Half of the transaction rows are deleted.
- Some transaction amounts are changed to negative values.
- Duplicate user records are inserted.

These corrupted inputs help test whether the system can detect backup problems before recovery.

## Expected Outputs Generated

After selecting a backup in the Streamlit dashboard, the user can run either:

- **Static Validation**
- **Dynamic AI Validation**

The expected outputs are:

1. Dashboard result showing `PASS` or `FAIL`.
2. Validation details shown on screen.
3. AI narrative report explaining the backup health.
4. Downloadable PDF report.
5. GitHub issue if validation fails and GitHub is configured.

## Included Sample Output Files

- [expected_static_pass_output.md](expected_static_pass_output.md)
- [expected_static_fail_output.md](expected_static_fail_output.md)
- [expected_ai_validation_output.md](expected_ai_validation_output.md)
- [sample_input_schema.sql](sample_input_schema.sql)

