# InvoiceCreatorApp

InvoiceCreatorApp is a WPF application designed to manage invoices and expenses, utilizing the Model-View-ViewModel (MVVM) pattern. The application allows users to create, update, and delete invoices, manage customer and company information, and generate monthly balance sheets to track income and expenses over a selected period.

## Features

- **Add, Update, and Delete Invoices**: Easily manage invoices by adding new products, updating existing ones, and removing unwanted items.
- **Manage Customer and Company Information**: Store and manage detailed information about customers and companies.
- **Automatic Calculation of Totals**: The application automatically calculates subtotals, VAT, and total amounts for each invoice.
- **Generate Monthly Balance Sheets**: Create balance sheets to review income and expenses over a specific period.
- **Input Validation**: Ensures that all necessary fields are correctly filled out before allowing actions like adding or saving an invoice.

## Usage

### Invoice Management

1. **Adding a Product to an Invoice**:
    - Fill in the customer, company, and product details.
    - Click the "Add" button to add the product to the current invoice.
    - The application validates the input data to ensure accuracy.

2. **Updating an Invoice**:
    - Select an existing product from the invoice list.
    - Modify the details in the input fields.
    - Click the "Update" button to save the changes.

3. **Deleting a Product from an Invoice**:
    - Select the product from the invoice list.
    - Click the "Delete" button to remove the product from the invoice.

4. **Saving an Invoice**:
    - Ensure all necessary details are filled in.
    - Click the "Save" button to save the invoice to the database.

### Monthly Balance Sheet

1. **Generating a Monthly Balance Sheet**:
    - Navigate to the monthly balance sheet view.
    - Select the desired start and end dates for the report.
    - The application displays all income and expenses within the selected period, along with the final balance.

## Class and Method Descriptions

### InvoiceViewModel

The `InvoiceViewModel` class handles the logic for managing invoices, including adding, updating, deleting, and saving invoices. It also manages commands related to these actions.

- **AddCommand**: Command to add a new product to the invoice.
- **UpdateCommand**: Command to update an existing product in the invoice.
- **DeleteCommand**: Command to delete a selected product from the invoice.
- **SaveCommand**: Command to save the current invoice.
- **MonthlyBalanceCommand**: Command to generate a monthly balance sheet.
- **UpdateInvoiceTotals()**: Updates the subtotal, VAT, and total amounts for the invoice.
- **UpdatePositions()**: Updates the positions of items in the invoice.

### MonthlyBalanceViewModel

The `MonthlyBalanceViewModel` class handles the logic for generating and displaying monthly balance sheets, including managing the start and end dates for the report period and calculating income and expenses.

- **StartDateSelected / EndDateSelected**: Selected start and end dates for the report.
- **StartDate / EndDate**: Start and end dates for the reporting period.
- **Income**: Total income for the selected period.
- **Expense**: Total expenses for the selected period.
- **FinalBalance**: Final balance for the selected period.
- **UpdateDisplayedInvoices()**: Updates the displayed invoices based on the selected dates.

### RelayCommand

The `RelayCommand` class implements the `ICommand` interface, allowing commands to be defined and executed based on specified conditions.

- **CanExecute(object parameter)**: Checks if the command can be executed.
- **Execute(object parameter)**: Executes the command.

### ViewModelBase

The `ViewModelBase` class provides the base functionality for view models, implementing the `INotifyPropertyChanged` interface to notify the UI about property changes.

- **OnPropertyChanged(string propertyName)**: Notifies the UI about property changes.

### InvoiceData

The `InvoiceData` class provides methods for managing the list of invoices.

- **AddInvoice(Invoice invoiceData)**: Adds an invoice to the list.
- **GetInvoices()**: Returns the list of invoices.

### ExampleExpenseData

The `ExampleExpenseData` class provides methods for managing the list of expenses.

- **GetExpenses()**: Returns the list of expenses.
- **AddRandomExpenses(Expense expense)**: Adds a random expense to the list.

### LoginViewModel

The `LoginViewModel` class handles the logic for the login view, including managing the username and password, displaying error messages, and executing the login command.

- **Username**: The username entered in the login form.
- **Password**: The password entered in the login form.
- **IsViewVisible**: Indicates whether the login view is visible.
- **ErrorMessage**: Error message displayed when login fails.
- **LoginCommand**: Command for the login process.
- **CanExecuteLoginCommand(object obj)**: Checks if the login command can be executed.
- **ExecuteLoginCommand(object obj)**: Executes the login command.

