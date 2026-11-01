# SpendWise Expense Service

Business brief: Freelancers need to track expenses against monthly budgets. Build validated expense entries, category filtering and monthly summaries. Milestones: 1. Expense listing; 2. Validated creation and updates; 3. Budget calculations and tests. Start a Django project, use PostgreSQL and provide documented API examples. Deliver implementation, tests and README. No pre-existing repository is bundled.

## DevSim ticket workflow
Clone this repository. Create a feature branch using the exact ticket key below. Push changes and open a PR against the default branch. DevSim links PRs authored by your connected GitHub account automatically.

### SPE-4B91-101: Initialize Django Project Structure and PostgreSQL Database Configuration
Branch: `feature/spe-4b91-101`

- Django project initialized with a clean directory structure adhering to best practices
- PostgreSQL database configured via environment variables in `settings.py` with connection pooling support
- `.env.example` file created documenting required configuration keys
- Unit/Integration test requirement: Verify database health check management command or simple startup test passes successfully against a live test database instance

### SPE-4B91-102: Implement Validated Expense Entry Model, Migration, and REST Endpoints
Branch: `feature/spe-4b91-102`

- `Expense` model created with fields: `amount` (Decimal), `category` (CharField/Enum), `description` (TextField), `date` (DateField), and `created_at`
- Model validation ensures expenses cannot have negative amounts and required fields are strictly validated
- DRF API views implemented supporting listing all expenses and creating new validated expense entries
- Unit/Integration test requirement: pytest/unittest suite covering model constraints, serializer validation errors, and HTTP 201/400 responses on endpoints

### SPE-4B91-103: Build Monthly Budget Summary Calculation Engine and Filtering
Branch: `feature/spe-4b91-103`

- Service layer function implemented to calculate total expenses grouped by category for any given calendar month
- Expense listing endpoint enhanced to support query parameter filtering by category and month/year
- Summary endpoint created returning total budgeted spend versus actual expenses
- Unit/Integration test requirement: Integration tests verifying that category filters and monthly summary aggregations return exact calculations across edge cases (e.g., month boundaries, empty categories)

