# task-dependencies-python
git clone https://github.com/LZTCODER-creator/task-dependencies-python.git
class Task:
    def __init__(self, name):
        self.name = name
        self.predecessors = []
        self.successors = []

    def add_predecessor(self, task):
        self.predecessors.append(task)
        task.add_successor(self)

    def add_successor(self, task):
        self.successors.append(task)
        task.add_predecessor(self)

def print_dependencies(task):
    print(f"Task {task.name} has predecessors: {[t.name for t in task.predecessors]}")
    print(f"Task {task.name} has successors: {[t.name for t in task.successors]}")
    print()

# Example usage:
task_a = Task("A")
task_b = Task("B")
task_c = Task("C")

task_b.add_predecessor(task_a)
task_c.add_predecessor(task_b)

# Print dependencies
print_dependencies(task_a)
print_dependencies(task_b)
print_dependencies(task_c)
cd task-dependencies-python
