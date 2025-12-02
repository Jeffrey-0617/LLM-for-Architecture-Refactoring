# LLM-Driven Multi-Agent Software Architecture Refactoring with Integrated Formal Verification

## Overview
This project implements a multi-agent approach to software architecture refactoring with LLMs and formal verification.

## Prerequisites

### Required Tools
1. **Wright# Modules for PAT Verifier**
   - Installation guide: [PAT.ADL Repository](https://github.com/cnacha/PAT.ADL/tree/master)
   - This tool is essential for formal verification of architecture designs
2. **Gephi: Knowledge Graph Visulization**
   - Installation guide: [Gephi](https://gephi.org/)

### Python Dependencies
- Python 3.11.9
- Required packages in requirements.txt
    ```bash
    pip install -r requirements.txt
    ```

## Project Structure

- **Baselines/**: Baselines Results
- **Evaluation/**: Experimental Results of Our Approach
- **Refactoring_data.xlsx**: Experimental Dataset (List of refactoring tasks)
- **GRAG_ADL_Syntax/**: Microsoft GraphRAG
  - **input/**: Input raw documentation for Knowledge Graph Generation
  - **output/**: Generated Knowledge Graph contents
  - **KnowLedgeGraph.gephi**: Knowledge Graph
- **Helpers/**: Core functions
- **parallelrun_refactoring.py**: The tool with Exploration-Selection Strategy

## Usage

Before running the tool, configure the following: (1) Replace API keys in `Helpers/refactoring.py` with your own LangChain and OpenAI API keys, (2) Set up GraphRAG configuration and update the path in `Helpers/querygrag.py` (3) Replace the IP address of your PAT verifier (with Wright# modules) in `Helpers/divide_adl.py`.



Run the tool using the parallel execution script:
```bash
python parallelrun_refactoring.py
```

To customize the execution:
- Adjust the number of refactoring tasks by modifying `start_index` and `end_index` in the script
- Change the number of parallel runs by modifying the range in `args_list`

The script generates two output files:
- `Refactoring_Execution_results.xlsx`: All execution results
- `Final_Refactoring_Execution_results.xlsx`: Results with minimal path changes

## Features
- Automated architecture refactoring using LLMs
- Formal verification of refactored designs
- Multi-agent approach for refactoring tasks
- Integration with Wright# architecture description language

