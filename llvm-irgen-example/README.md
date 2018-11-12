
# LLVM IRGen Example

In this example, a C++ source code generating below LLVM IR through LLVM IRGen module is presented:

```
; ModuleID = 'foo_dead_recursive_loop'
source_filename = "foo_dead_recursive_loop"

define void @foo() {
entry:
  call void @foo()
  ret void
}
```

You can build it with command as below once you have llvm developing libraries installed.

```sh
c++ llvm-irgen-example.cpp -o llvm-irgen-example `llvm-config --cxxflags --ldflags --libs --system-libs`  
```
