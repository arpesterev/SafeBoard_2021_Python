# SafeBoard 2021: Python task

A Selenium-based browser testing exercise for the SafeBoard 2021 selection. The tests automate registration, login and other flows in a bundled local web application called `testmart`.

## Repository layout

- [`main.py`](main.py): Python `unittest` test cases.
- [`initial.py`](initial.py): starts the local application and creates a Selenium driver.
- [`page_object.py`](page_object.py) and [`page_locators.py`](page_locators.py): page objects and element locators.
- [`testmart_data.py`](testmart_data.py): test input data.
- [`test/`](test/): bundled application executable.
- [`web_driver/`](web_driver/): checked-in browser drivers.

## Environment and execution

The repository declares `selenium` and `pytest` in `requirements.txt`:

```sh
python -m pip install -r requirements.txt
```

The test script expects the local application to be available at `http://localhost:8080` and starts it from the `test/` directory. Browser-driver paths are configured in `main.py`.

**Known limitation:** `main.py` imports `testmart_pages`, but that module is not present among the checked-in files. The Selenium driver setup also uses an older API. These issues need to be resolved before running the suite on a modern environment. No tests were run for this documentation change.

This is a historical test exercise, not a maintained web-testing framework.
