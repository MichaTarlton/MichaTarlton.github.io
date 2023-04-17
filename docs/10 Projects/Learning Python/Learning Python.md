---
aliases: python
type: [project, dev]
project: python
status: open
priority: p4
creationtag: 2023-02-08 12:10
infotags: [dev, development, documentation, py, python]
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"Learning Python")
GROUP BY type
SORT file.ctime asc 
```
## Statement
FOr now this is just a junkyard / scratch pad to collect random python stuff

# Scratch pad
## `with` statement
[with statement in Python - GeeksforGeeks](https://www.geeksforgeeks.org/with-statement-in-python/)

> In Python, **with statement** is used in exception handling to make the code cleaner and much more readable. It simplifies the management of common resources like file streams. Observe the following code example on how the use of with statement makes code cleaner.

Typically used for file handling as I’ve seen so far

- [ ] I need to learn how to use #python debugger⏫ #p1 #dev 
[[Cross Entropy]]


## `Super`
> `super()` lets you avoid referring to the base class explicitly, which can be nice. But the main advantage comes with multiple inheritance, where all sorts of [fun stuff](http://www.artima.com/weblogs/viewpost.jsp?thread=236275) can happen. See the [standard docs on super](https://docs.python.org/2/library/functions.html#super) if you haven't already.
> 
> Note that [the syntax changed in Python 3.0](https://docs.python.org/3/library/functions.html#super): you can just say `super().__init__()` instead of `super(ChildB, self).__init__()` which IMO is quite a bit nicer. The standard docs also refer to a [guide to using `super()`](https://rhettinger.wordpress.com/2011/05/26/super-considered-super/) which is quite explanatory.
- https://stackoverflow.com/questions/576169/understanding-python-super-with-init-methods

Did research on it elsewhere:
![[HF DRL Coding - Unit 4#super Policy self]]


# Pytorch
PyTorch uses `torch.tensor`, rather than numpy arrays, so we need to convert our data.

TOrch tutorial and colab is pretty great: https://pytorch.org/tutorials/beginner/nn_tutorial.html
Made a colab notebook here: https://colab.research.google.com/drive/1nIPsZdTWmpu7mrBiSWL9i6JKwnzOVx4E?usp=sharing

Doing a lot of function definition

## Pytorch Summary
-   **torch.nn**
    -   `Module`: creates a callable which behaves like a function, but can also contain state(such as neural net layer weights). It knows what `Parameter` (s) it contains and can zero all their gradients, loop through them for weight updates, etc.
    -   `Parameter`: a wrapper for a tensor that tells a `Module` that it has weights that need updating during backprop. Only tensors with the `requires_grad` attribute set are updated
    -   `functional`: a module(usually imported into the `F` namespace by convention) which contains activation functions, loss functions, etc, as well as non-stateful versions of layers such as convolutional and linear layers.
-   `torch.optim`: Contains optimizers such as `SGD`, which update the weights of `Parameter` during the backward step
    
-   `Dataset`: An abstract interface of objects with a `__len__` and a `__getitem__`, including classes provided with Pytorch such as `TensorDataset`
    
-   `DataLoader`: Takes any `Dataset` and creates an iterator which returns batches of data.


## `nn.Module`
A python class for pytorch functions
> Next up, we'll use `nn.Module` and `nn.Parameter`, for a clearer and more concise training loop. We subclass `nn.Module` (which itself is a class and able to keep track of state). In this case, we want to create a class that holds our weights, bias, and method for the forward step. `nn.Module` has a number of attributes and methods (such as `.parameters()` and `.zero_grad()`) which we will be using.
> 
> Note> 
> `nn.Module` (uppercase M) is a PyTorch specific concept, and is a class we'll be using a lot. ``nn.Module`` is not to be confused with the Python concept of a (lowercase ``m``) [module](https://docs.python.org/3/tutorial/modules.html), which is a file of Python code that can be imported.

## `nn.linear`
> We continue to refactor our code. Instead of manually defining and initializing `self.weights` and `self.bias`, and calculating `xb @ self.weights + self.bias`, we will instead use the Pytorch class [nn.Linear](https://pytorch.org/docs/stable/nn.html#linear-layers) for a linear layer, which does all that for us. Pytorch has many types of predefined layers that can greatly simplify our code, and often makes it faster too.
- From pytorch tutorial

From: https://pytorch.org/docs/stable/nn.html#linear-layers
>  [`nn.Linear`](https://pytorch.org/docs/stable/generated/torch.nn.Linear.html#torch.nn.Linear "torch.nn.Linear")
 Applies a linear transformation to the incoming data: $y = xA^T + b$


## `torch.optim`
> Pytorch also has a package with various optimization algorithms, torch.optim. We can use the step method from our optimizer to take a forward step, instead of manually updating each parameter.
> 
> **This will let us replace our previous manually coded optimization step**:
> with torch.no_grad(): for p in model.parameters(): p -= p.grad * lr model.zero_grad()
> 
> **and instead use just**:
> opt.step() opt.zero_grad()
> 
> (optim.zero_grad() resets the gradient to 0 and we need to call it before computing the gradient for the next minibatch.)

## Pytorch Dataset
> PyTorch has an abstract Dataset class. A Dataset can be anything that has a `__len__` function (called by Python's standard `len` function) and a `__getitem__` function as a way of indexing into it. [This tutorial](https://pytorch.org/tutorials/beginner/data_loading_tutorial.html) walks through a nice example of creating a custom `FacialLandmarkDataset` class as a subclass of `Dataset`.
>
> PyTorch's [TensorDataset](https://pytorch.org/docs/stable/_modules/torch/utils/data/dataset.html#TensorDataset) is a Dataset wrapping tensors. By defining a length and way of indexing, this also gives us a way to iterate, index, and slice along the first dimension of a tensor. This will make it easier to access both the independent and dependent variables in the same line as we train.

## DataLoader
> Pytorch's `DataLoader` is responsible for managing batches. You can create a `DataLoader` from any `Dataset`. `DataLoader` makes it easier to iterate over batches. Rather than having to use `train_ds[i*bs : i*bs+bs]`, the DataLoader gives us each minibatch automatically.

## [TORCH.TENSOR.VIEW](https://pytorch.org/docs/stable/generated/torch.Tensor.view.html#torch-tensor-view)

Tensor.view(_*shape_) → [Tensor](https://pytorch.org/docs/stable/tensors.html#torch.Tensor "torch.Tensor")[](https://pytorch.org/docs/stable/generated/torch.Tensor.view.html#torch.Tensor.view)

Returns a new tensor with the same data as the `self` tensor but of a different `shape`.
[torch.Tensor.view — PyTorch 1.13 documentation](https://pytorch.org/docs/stable/generated/torch.Tensor.view.html#torch-tensor-view)

## Momentum
See: https://cs231n.github.io/neural-networks-3/#sgd
>  a variation on stochastic gradient descent that takes previous updates into account as well and generally leads to faster training.

Actually a pretty cool idea of how to optimize [[Stochastic Gradient Descent|SGD]]


## Sequential
> `torch.nn` has another handy class we can use to simplify our code: [Sequential](https://pytorch.org/docs/stable/nn.html#torch.nn.Sequential) . A `Sequential` object runs each of the modules contained within it, in a sequential manner. This is a simpler way of writing our neural network.

> To take advantage of this, we need to be able to easily define a **custom layer** from a given function. For instance, PyTorch doesn't have a `view` layer, and we need to create one for our network. `Lambda` will create a layer that we can then use when defining a network with `Sequential`.

## nn.linear
https://pytorch.org/docs/stable/generated/torch.nn.Linear.html
Applies a linear transformation to the incoming data: $y = xA^T + b$


---

## Torch tutorial
<iframe src="https://pytorch.org/tutorials/beginner/nn_tutorial.html" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>