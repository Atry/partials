The original codes are as follows:
```scala
def softmax(implicit scores: INDArray @Symbolic): INDArray @Symbolic = {
  val expScores = exp(scores)
  expScores / expScores.sum(1)
}
```
If we need to view the state after `exp(scores)`, we shall add a line of codes after `exp(scores)`, as follows:
```scala
def softmax(implicit scores: INDArray @Symbolic): INDArray @Symbolic = {
  val expScores: INDArray @Symbolic  = exp(scores)
    .withOutputDataHook{ data: INDArray => println(data) }
  expScores / expScores.sum(1)
}
```

We can omit the type and shorten it as follows (there may occur a warning, which can be neglected):
```scala
def softmax(implicit scores: INDArray @Symbolic): INDArray @Symbolic = {
  val expScores = exp(scores)
    .withOutputDataHook{ data => println(data) }
  expScores / expScores.sum(1)
}
```

The method signature of `withOutputDataHook` under `com.thoughtworks.deeplearning#DifferentiableAny`
```scala, is as follows:
def withOutputDataHook(hook: OutputData => Unit): Layer.Aux[Input, Batch.Aux[OutputData, OutputDelta]] = ???
```

When invoking this method, we can transfer in a customized method for putting out or performing other operation, and type breakpoints on this customized method to view the state after `exp(scores)`.
In case the debug is not needed, the newly added line can be commented out, which will not affect codes at other locations.