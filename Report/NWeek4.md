Merged \
&emsp;[[SelectionDAG] Lowering usub.sat(a, 1) to a - (a != 0)](https://github.com/llvm/llvm-project/pull/170076)  \
&emsp;优化这种序列
```
  	addi	a1, a0, -1
	sltu	a0, a0, a1
	addi	a0, a0, -1
	and	a0, a0, a1
	ret
```
变成
```
  movl %edi, %eax
  cmpl $1, %edi
  adcl $-1, %eax
  retq
```
In progress \
&emsp;[优化寄存器序列](https://github.com/llvm/llvm-project/pull/163047) 按要求修改了下，不太可能合并\
&emsp;[在nchw格式转nhwc格式转换的时候会crasg](https://github.com/llvm/llvm-project/pull/171122)
