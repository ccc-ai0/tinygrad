
```
$ python serious_mnist.py
loss 2.31 accuracy 0.09:   0%|                       | 1/1875 [02:24<75:15:10, 144.56s/it]
Traceback (most recent call last):
  File "D:\ccc\ccc112b\tinygrad\examples\serious_mnist.py", line 134, in <module>
    train(model, X_aug, Y_train, optimizer, steps=steps, lossfn=lossfn, BS=BS)
  File "d:\ccc\ccc112b\tinygrad\extra\training.py", line 32, in train
    loss, accuracy = train_step(x, y)
                     ^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\features\jit.py", line 122, in __call__
    self.ret = self.fxn(*args, **kwargs)
               ^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\extra\training.py", line 18, in train_step
    optim.step()
  File "d:\ccc\ccc112b\tinygrad\tinygrad\nn\optim.py", line 24, in step
    def step(self, extra:Optional[List[Tensor]]=None): self.realize(self._step() + (extra if extra is not None else []))
                                                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\nn\optim.py", line 22, in realize
    Tensor.corealize(extra + self.params + self.buffers if extra is not None else self.params + self.buffers)
  File "d:\ccc\ccc112b\tinygrad\tinygrad\tensor.py", line 135, in corealize
    run_schedule(create_schedule(flatten([x.lazydata.lbs if isinstance(x.lazydata, MultiLazyBuffer) else [x.lazydata] for x in lst])))
  File "d:\ccc\ccc112b\tinygrad\tinygrad\realize.py", line 49, in run_schedule
    prg = lower_schedule_item(si)
          ^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\realize.py", line 31, in lower_schedule_item
    if si.ast[0].op is BufferOps.STORE: return Device[si.outputs[0].device].get_runner(*si.ast)
                                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\device.py", line 288, in get_runner
    def get_runner(self, *ast:LazyOp) -> CompiledASTRunner: return self.to_program(self.get_linearizer(*ast))
                                                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\device.py", line 255, in to_program
    ret = CompiledASTRunner(k.name, self.compiler.render(to_function_name(k.name), k.uops), self.dname, k.global_size, k.local_size,
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\device.py", line 205, in __init__
    lib:bytes = precompiled if precompiled is not None else self.device.compiler.compile_cached(prg)
                                                            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\device.py", line 191, in compile_cached
    lib = self.compile(src)
          ^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\runtime\ops_gpu.py", line 30, in compile
    raise RuntimeError(f"OpenCL Compile Error\n\n{ctypes.string_at(mstr, size=log_size.value).decode()}")
RuntimeError: OpenCL Compile Error
```
