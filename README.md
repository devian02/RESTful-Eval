# RESTful-Eval

> **🚀 Project Draft Notice**  
> This is a draft of the RESTful-Eval project, under active development. The scope, metrics, and implementation details may evolve during the Winter Semester 2025 as the research progresses. Stay tuned for updates!



[![Project Status](https://img.shields.io/badge/status-active-success.svg)]()
[![Academic Research](https://img.shields.io/badge/Academic_Research-Bachelor_Semester_Project-lightgrey)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

[![Python](https://img.shields.io/badge/Python-3.8+-blue)](https://www.python.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript)]()
[![Java](https://img.shields.io/badge/Java-17+-red?logo=openjdk)]()
[![JMeter](https://img.shields.io/badge/JMeter-5.5+-orange)](https://jmeter.apache.org/)

[![Research Focus](https://img.shields.io/badge/Focus-Reliability_|_Maintainability_|_Efficiency-blue)]()
[![Benchmarks](https://img.shields.io/badge/Benchmarks-Automated-blueviolet)]()
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-success)]()

> **🎓 Academic Project**  
> RESTful-Eval is my Bachelor Semester Project as a Computer Science student at the University of Luxembourg, developed under the supervision and guidance of my tutor, Davide Corradini, whom I sincerely thank for his invaluable support.

## Overview

RESTful-Eval is intended as a tool for evaluating modern backend languages (TypeScript, Python, and Java) and frameworks (Express.js, Deno with Oak, Bun with Elysia, Flask, FastAPI, Django, Spring Boot) in RESTful API development. It focuses on **Reliability**, **Maintainability**, and **Efficiency**, using automated benchmarking and qualitative analysis to guide technology stack selection.

## Scientific Question

How do reliability, maintainability, and efficiency manifest across modern backend languages, runtimes, and frameworks in RESTful API development, and how can these factors inform optimal technology stack choices?

## Features

- **Standardized APIs**: Uniform endpoints across frameworks for fair comparison.
- **Automated Benchmarking**: Python-driven JMeter tests and `psutil` for resource monitoring.
- **Comprehensive Metrics**:
  - **Reliability**: Type safety score, error recovery rate, crash rate, memory leak rate.
  - **Maintainability**: Cyclomatic complexity, Maintainability Index, dependency health.
  - **Efficiency**: Throughput, latency, CPU, and memory usage.
- **Structured Outputs**: JSON/CSV results for analysis.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/username/RESTful-Eval.git
   ```
2. Navigate to the project directory:
   ```bash
   cd RESTful-Eval
   ```
3. Install Python dependencies:
   ```bash
   pip install psutil rad
   ```
4. Install Apache JMeter (v5.5+) and configure `benchmarks/load_test.jmx`.
5. Set up language-specific dependencies (see `/src/<language>/README.md`).

## Usage

1. **Launch APIs**: Start APIs in `/src/<language>/<framework>` (e.g., `npm run start`, `python app.py`).
2. **Run Benchmarks**: Execute the benchmarking tool:
   ```bash
   python benchmarks/run_benchmarks.py
   ```
3. **Review Results**: Check metrics in `/benchmarks/results`.

## Project Structure

```
RESTful-Eval/
├── src/                    # API implementations
│   ├── typescript/         # Node.js (Express.js), Deno (Oak), Bun (Elysia)
│   ├── python/             # Flask, FastAPI, Django (CPython)
│   ├── java/               # Spring Boot (JVM)
├── benchmarks/             # Benchmarking scripts and results
│   ├── run_benchmarks.py   # Core benchmarking tool
│   ├── load_test.jmx       # JMeter test plan
│   ├── results/            # JSON and CSV outputs
├── docs/                   # Analysis and documentation
└── README.md               # Tool overview
```

## Methodology and Metrics

- **API Implementation**: Identical endpoints with CPU- and I/O-bound operations.
- **Reliability**:
  - **Type Safety**: \(\frac{\text{Type errors caught}}{\text{Total type errors}}\) using `mypy`/`tsc`.
  - **Error Handling**: \(\frac{\text{Handled errors}}{\text{Total errors}}\) via JMeter response codes.
  - **Stability**: Crash rate (\(\frac{\text{Crashes}}{\text{Test runs}}\)) and memory leak rate (\(\frac{\Delta \text{Memory}}{\text{Duration}}\)) with `psutil`.
- **Maintainability**:
  - **Readability/Modularity**: Cyclomatic complexity (\(E - N + 2P\)) and Maintainability Index using `radon`.
  - **Dependency Management**: \(\frac{\text{Up-to-date deps}}{\text{Total deps}} \times (1 - \text{Deprecated deps})\) with `pipdeptree`.
- **Efficiency**:
  - **Performance**: Throughput (\(\frac{\text{Requests}}{\text{Time}}\)) and latency (\(\frac{\sum \text{Response time}}{\text{Requests}}\)) via JMeter.
  - **Resource Usage**: Average CPU/memory usage with `psutil`.

## Technology Stack

- **TypeScript**: Node.js (Express.js), Deno (Oak), Bun (Elysia).
- **Python**: Flask, FastAPI, Django (CPython).
- **Java**: Spring Boot (JVM).
- **Tooling**: Apache JMeter, Python (`psutil`, `radon`, `pipdeptree`).


## Expected Outcome

RESTful-Eval delivers data-driven insights into backend technologies, combining empirical metrics and qualitative analysis to guide developers and researchers in selecting reliable, maintainable, and efficient frameworks for RESTful APIs.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

Adhere to coding standards and include documentation.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For feedback or issues open an issue. Thank you!
