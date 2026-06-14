# LangGraph Recipes - A Methodical Learning Path

A comprehensive, hands-on guide to mastering **LangGraph** through progressive examples and practical workflows. This repository provides a structured learning journey from fundamental concepts to advanced workflow patterns.

## 📚 Overview

LangGraph is a library for building stateful, multi-actor applications with LLMs. This repository demonstrates how to design and implement various workflow patterns using LangGraph's core concepts: **state graphs**, **nodes**, **edges**, and **execution flows**.

Each notebook builds upon the previous one, introducing new concepts while reinforcing core ideas. With 8 progressive notebooks, you'll advance from fundamentals to production-ready parallel workflows.

## 🎯 Learning Path

### **Notebook 1: Introduction to LangGraph** (`01_intro_to_langgraph.ipynb`)
**Topics:** State graphs, nodes, edges, and basic execution

- Define state schemas using `TypedDict`
- Create nodes that process and transform state
- Build graphs with `StateGraph`
- Connect nodes using edges
- Compile and execute graphs

**Concepts:** START, END, state management, graph compilation

---

### **Notebook 2: Practical Example 1** (`02_practical_example1.ipynb`)
**Topics:** Building your first practical workflow

- Implement a simple multi-node workflow
- Practice state transitions between nodes
- Visualize graph structure
- Execute workflows with initial state

**Key Skills:** Graph construction, node implementation, execution flow

---

### **Notebook 3: Practical Example 2** (`03_practical_example2.ipynb`)
**Topics:** Conditional logic and branching

- Implement conditional edges based on state
- Build a calculator-like workflow
- Handle multiple execution paths
- Process state conditionally

**Concepts:** Conditional logic, branching workflows, decision nodes

---

### **Notebook 4: Sequential Workflow** (`04_sequential_workflow.ipynb`)
**Topics:** Sequential processing pipelines

- Design recipe formatting workflow
- Process data through multiple sequential steps
- Validate state at different stages
- Aggregate results from multiple processors

**Project:** Recipe formatter that processes ingredients and instructions sequentially

---

### **Notebook 5: LLM Workflow** (`05_llm_workflow.ipynb`)
**Topics:** Integrating LLMs into workflows

- Initialize language models (OpenAI)
- Use LLMs as workflow nodes
- Chain LLM calls together
- Handle LLM outputs in state

**Technologies:** LangChain, ChatOpenAI, prompt engineering

---

### **Notebook 6: Prompt Chaining** (`06_prompt_chaining.ipynb`)
**Topics:** Advanced prompt engineering and multi-step LLM reasoning

- Chain multiple LLM prompts together
- Use ChatPromptTemplate for structured prompts
- Generate content through multiple LLM passes
- Implement multi-stage content generation

**Project:** Story writer that generates content in multiple steps

---

### **Notebook 7: Parallel Workflow** (`07_parallel_workflow.ipynb`)
**Topics:** Concurrent execution patterns

- Design parallel processing workflows
- Execute multiple nodes simultaneously
- Merge results from parallel branches
- Optimize workflow performance

**Concepts:** Parallelization, resource efficiency, concurrent execution

---

### **Notebook 8: Advanced Parallel Workflow** (`08_advanced_parallel_workflow.ipynb`)
**Topics:** Complex multi-branch parallel workflows with LLMs

- Create sophisticated parallel workflows with multiple concurrent branches
- Process content through multiple analysis paths simultaneously
- Integrate LLM calls in parallel branches
- Merge and aggregate results from different processors
- Build production-ready content processing pipelines

**Project:** Story processor that generates content and creates quizzes, ratings, and improvement suggestions in parallel

**Concepts:** Advanced parallelization, multi-branch workflows, LLM integration in parallel, result aggregation

---

## 🚀 Getting Started

### Prerequisites

- Python 3.12+
- pip or uv package manager
- OpenAI API key (for LLM-based notebooks)

### Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd langgraph-recipes
   ```

2. **Install dependencies:**
   ```bash
   pip install -e .
   ```
   
   Or with uv:
   ```bash
   uv sync
   ```

3. **Install Jupyter (if not already installed):**
   ```bash
   pip install jupyter
   ```

### Configuration

Set your OpenAI API key as an environment variable:

```bash
export OPENAI_API_KEY="your-api-key-here"
```

## 📖 How to Use

### Running Individual Notebooks

1. **Start Jupyter:**
   ```bash
   jupyter notebook
   ```

2. **Navigate to a notebook** and run cells sequentially from top to bottom

3. **Follow the progression** from Notebook 1 to 8 for the best learning experience

### Recommended Approach

- **Read the code comments** in each cell
- **Run cells one at a time** to understand execution flow
- **Modify examples** to experiment with concepts
- **Visualize graphs** using the included visualization cells
- **Execute workflows** with different inputs to see how state changes

## 🏗️ Project Structure

```
langgraph-recipes/
├── 01_intro_to_langgraph.ipynb          # Fundamentals
├── 02_practical_example1.ipynb          # First workflow
├── 03_practical_example2.ipynb          # Branching logic
├── 04_sequential_workflow.ipynb         # Multi-stage processing
├── 05_llm_workflow.ipynb                # LLM integration
├── 06_prompt_chaining.ipynb             # Advanced LLM patterns
├── 07_parallel_workflow.ipynb           # Concurrent execution
├── 08_advanced_parallel_workflow.ipynb  # Complex parallel workflows with LLMs
├── main.py                              # Standalone entry point
├── pyproject.toml                       # Project configuration
└── README.md                            # This file
```

## 🔑 Key Concepts

### State Schema
Define the structure of data flowing through your graph using `TypedDict`:
```python
class MyState(TypedDict):
    text: str
    count: int
```

### Nodes
Functions that process state and return updated state:
```python
def process_node(state: MyState) -> MyState:
    return {"text": state["text"] + " processed"}
```

### Edges
Connections between nodes that define execution flow:
```python
graph.add_edge(START, "node_name")
graph.add_edge("node_a", "node_b")
graph.add_edge("node_b", END)
```

### Graph Compilation
Transform your graph definition into an executable application:
```python
app = graph.compile()
result = app.invoke(initial_state)
```

## 📊 Graph Visualization

Most notebooks include visualization cells using:
```python
app.get_graph().draw_mermaid_png()
```

This helps you understand the workflow structure and execution paths.

## 💡 Learning Tips

1. **Start Simple:** Begin with Notebook 1 and progress sequentially
2. **Understand State:** Grasp how state flows through your graph
3. **Experiment:** Modify examples and observe how state changes
4. **Visualize:** Use graph visualization to understand complex workflows
5. **Build Projects:** Apply concepts to your own problems

## 🛠️ Technologies Used

- **LangGraph**: Graph-based application framework
- **LangChain**: LLM framework and prompt management
- **OpenAI API**: Language model provider
- **Python 3.12+**: Programming language
- **Jupyter Notebooks**: Interactive learning environment

## 📝 Exercises & Extensions

Each notebook includes cells for experimentation. Try these challenges:

1. **Notebook 1-3:** Modify node functions and edges
2. **Notebook 4:** Add new workflow steps or validation rules
3. **Notebook 5-6:** Experiment with different prompts and LLM models
4. **Notebook 7:** Create your own parallel workflow patterns

## 🤝 Contributing

Feel free to improve examples, add clarifications, or create new recipes. Follow the existing structure and style.

## 📄 License

This project is provided as-is for educational purposes.

## 🔗 Resources

- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [LangChain Documentation](https://python.langchain.com/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)

---

**Happy Learning! 🚀**

Start with `01_intro_to_langgraph.ipynb` and progress through all 8 notebooks in order for the best learning experience.
