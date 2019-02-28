# Class Based vs Function Based Views 

[Resource](https://simpleisbetterthancomplex.com/article/2017/03/21/class-based-views-vs-function-based-views.html)

We will be using function based views during most sprints - ignore any class based views you may find online! Function based views allow you to manipulate your data in a less abstract way, as well as a bit more customized way (you can set more “rules” in a function based view)

Class based:
```python
class Employee_Detail_View(DetailView):
    model = Employee
    context_object_name = 'Employee_Detail'
    template_name = 'WorkforceManagement/Employee_Detail.html'
```

Function based:
```python
def Computer_Detail_View(request, pk):
    computer = get_object_or_404(Computer, pk=pk)
    return render(request, 'WorkforceManagement/Computer_Detail.html', {'computer': computer})
```
