# python-oop-review

## Overview

**python-oop-review** is a Python console application designed to illustrate the core concepts of Object-Oriented Programming (OOP) using a process simulation. The project implements a simple compilation pipeline—converting a source file (`main.c`) into an executable (`main.exe`)—to demonstrate encapsulation, inheritance, polymorphism, and abstraction. A `Process` manages a sequence of `Task` objects (e.g., scanning, parsing, static analysis, code generation, linking), utilizing resources like `Consumable` Memory and `Usable` CPU.

**Author**: IoT Solution Development Staff  
**Date**: March 27, 2025  
**Version**: 1.0  
**License**: MIT

## Purpose

The primary goal of `python-oop-review` is educational: to provide a practical example of OOP principles in Python through a process simulation. It serves as a learning tool for developers to explore:
- **Encapsulation**: Data and behavior are bundled within classes (e.g., `Resource`, `Task`).
- **Inheritance**: Classes like `ConsumableResource` and `UsableResource` inherit from `Resource`.
- **Polymorphism**: Abstract methods (e.g., `execute`) allow runtime behavior variation.
- **Abstraction**: Abstract base classes (`Resource`, `Executable`) define interfaces.

## Features

- **OOP Demonstration**: Showcases encapsulation, inheritance, polymorphism, and abstraction in Python.
- **Modular Design**: Classes are organized in separate files within the `src/` directory.
- **Process Simulation**: Models a compilation pipeline with realistic tasks and resource management.
- **Resource Types**: Includes `ConsumableResource` (depletes) and `UsableResource` (reusable).
- **Exception Handling**: Simple error handling for resource allocation and execution.
- **Documentation**: Detailed docstrings for classes, attributes, and methods.

## Class Diagram
Following is the class diagram representing the relationships between classes in the project:

![Class Diagram](https://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/upc-pre-202520-1asi0572-3479/python-oop-review/refs/heads/master/docs/class-diagram.puml)

## Prerequisites

- **Python**: Version 3.13 or higher
- **IDE (Optional)**: PyCharm, VSCode, or any Python-supporting editor

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/upc-pre-202520-1asi0572-3479/python-oop-review.git
   cd python-oop-review