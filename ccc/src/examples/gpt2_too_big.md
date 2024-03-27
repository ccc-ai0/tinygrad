

1.52G...

```
$ python gpt2.py
using GPU backend
using gpt2-medium
https://huggingface.co/gpt2-medium/resolve/main/pytorch_model.bin:   0%| | 2.49M/1.52G [00:14<2:08:35, 197kTraceback (most recent call last):
  File "D:\ccc\ccc112b\tinygrad\examples\gpt2.py", line 196, in <module>
    gpt2 = GPT2.build(args.model_size)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "D:\ccc\ccc112b\tinygrad\examples\gpt2.py", line 131, in build
    weights = torch_load(fetch(f'https://huggingface.co/{model_size}/resolve/main/pytorch_model.bin'))
                         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "d:\ccc\ccc112b\tinygrad\tinygrad\helpers.py", line 190, in fetch
    while chunk := r.read(16384): progress_bar.update(f.write(chunk))
                   ^^^^^^^^^^^^^
  File "C:\Users\user\AppData\Local\Programs\Python\Python311\Lib\http\client.py", line 466, in read
    s = self.fp.read(amt)
        ^^^^^^^^^^^^^^^^^
  File "C:\Users\user\AppData\Local\Programs\Python\Python311\Lib\socket.py", line 706, in readinto
    return self._sock.recv_into(b)
           ^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\user\AppData\Local\Programs\Python\Python311\Lib\ssl.py", line 1278, in recv_into
    return self.read(nbytes, buffer)
           ^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\user\AppData\Local\Programs\Python\Python311\Lib\ssl.py", line 1134, in read
    return self._sslobj.read(len, buffer)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KeyboardInterrupt
https://huggingface.co/gpt2-medium/resolve/main/pytorch_model.bin:   0%| | 2.51M/1.52G [00:15<2:38:13, 160k
```