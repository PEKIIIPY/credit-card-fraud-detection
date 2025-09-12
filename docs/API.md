# API Documentation

## Data Preprocessing Module

### `load_and_validate_data(filepath: str) -> pd.DataFrame`
Loads and validates credit card transaction data from CSV file.

### `create_balanced_dataset(data: pd.DataFrame, target_column: str = 'Class') -> pd.DataFrame`
Creates balanced dataset using under-sampling technique.

## Model Evaluation Module

### `evaluate_model_performance(y_true: np.ndarray, y_pred: np.ndarray) -> Dict[str, float]`
Calculates comprehensive performance metrics.

### `print_model_report(y_true: np.ndarray, y_pred: np.ndarray, dataset_name: str = "Dataset")`
Prints detailed evaluation report.