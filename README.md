# playwright---YUVANSANDAR-J
# 🧪 Playwright + Pytest Automation Framework (Myntra Testing)

## 📌 Overview

This project is a **UI automation testing framework** built using:

* **Playwright (Python)** for browser automation
* **Pytest** for test execution
* **Pytest-xdist** for parallel execution
* **Pytest-html** for reporting

It is designed to:

* Automate product search and cart flow on Myntra
* Run tests in parallel
* Capture screenshots for **failed and XFAIL tests**
* Generate a detailed **HTML report with embedded screenshots**

---

## 🚀 Features

* ✅ Parallel test execution (`-n 4`)
* 📸 Automatic screenshot capture for:

  * Failed tests
  * XFAIL tests
* 📊 HTML report generation with screenshots
* 🔁 Retry-safe navigation for unstable websites
* 🧩 Modular and scalable test structure

---

## 📁 Project Structure

```
playwright_updated/
│
├── tests/
│   └── test_all.py        # All test cases
│
├── screenshots/           # Auto-saved screenshots
├── reports/               # HTML reports
│
├── conftest.py            # Fixtures + hooks
├── pytest.ini             # Pytest configuration
└── README.md              # Documentation
```

---

## ⚙️ Installation

### 1. Create Virtual Environment

```
python -m venv venv
venv\Scripts\activate
```

### 2. Install Dependencies

```
pip install playwright pytest pytest-xdist pytest-html
playwright install
```

---

## ▶️ Running Tests

### Run with Parallel Execution

```
pytest
```

### Run with Specific Workers

```
pytest -n 4
```

---

## 📸 Screenshots

* Screenshots are automatically captured for:

  * ❌ Failed tests
  * ⚠️ XFAIL tests

📂 Location:

```
screenshots/
```

---

## 📊 HTML Report

After execution, open:

```
reports/report.html
```

### Report Includes:

* Test summary (Pass / Fail / XFAIL)
* Execution time
* Embedded screenshots for failures

---

## 🧪 Test Types Included

### ✅ Working Tests

* Product search
* Add to bag
* Cart open
* Multiple item search

### ❌ Failing Tests (for demo)

* Wrong selector
* No size selected
* No wait condition

These are marked with:

```
@pytest.mark.xfail
```

---

## 🔥 Key Implementation Details

### Screenshot Hook

* Uses `pytest_runtest_makereport`
* Captures both:

  * `rep.failed`
  * `rep.outcome == "skipped"` (XFAIL)

### Parallel Stability

* Uses:

```
--dist=loadscope
```

* Prevents server overload issues

---

## ⚠️ Known Limitations

* Myntra may:

  * Block automation requests
  * Delay page loads
* Parallel execution may cause:

  * Network throttling
  * Occasional timeouts

---

## ✅ Best Practices

* Use `safe_goto()` for navigation retries
* Avoid heavy parallel load (`-n 2` if unstable)
* Keep selectors robust
* Use waits instead of timeouts

---

## 🎯 Example Output

### Terminal

```
PASSED tests/test_all.py::test_search_product
XFAIL tests/test_fail_cases.py::test_fail_wrong_selector
FAILED tests/test_add_to_bag
```

### Screenshot

```
screenshots/tests_test_add_to_bag.png
```

---

## 🔮 Future Enhancements

* 🎥 Video recording for failed tests
* 🔁 Auto-retry failed tests
* 📈 Allure reporting integration
* 🤖 Stealth mode to avoid blocking

---

## 👨‍💻 Author

Developed for automation testing practice using Playwright + Pytest.

---

## ⭐ Summary

This framework provides:
✔ Parallel execution
✔ Screenshot capture for failures & XFAIL
✔ HTML reporting
✔ Stable automation structure

---

👉 Ready for real-world automation testing 🚀

