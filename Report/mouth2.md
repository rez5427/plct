Merged PR \
&emsp;https://github.com/riscv/sail-riscv/pull/577   v扩展使用了空的vm_val导致mask全为0，即等同于指令未运行 | \
&emsp;https://github.com/riscv/sail-riscv/pull/581   错误的使用了sign,在riscv spec里隐含的定义了当一个数需要扩展并且位数小于xlen的时候，需要用unsign扩展 | \
&emsp;https://github.com/riscv/sail-riscv/pull/585   错误的在硬件层面对vxsat进行复位为0，此举应该为csr相关指令去复位 | \
&emsp;https://github.com/riscv/sail-riscv/pull/564   对vxrm csr寄存器重复定义，导致没有真正写入正确的vxrm. |

---- 上面四个使sail-riscv可以运行通过riscv-vector-tests的测试（但是没有并入sail-riscv的指令没有测试)

&emsp;https://github.com/riscv/sail-riscv/pull/590 使得sail-riscv可以设置vlen和elen，不再使用register定义这两个数 |---- 这两个是一点重构工作 \
&emsp;https://github.com/riscv/sail-riscv/pull/607 在上一个pr的基础上改变定义vlenb的逻辑 |

&emsp;https://github.com/riscv/sail-riscv/pull/586 优化代码，使其更简洁，更易读

In progress \
&emsp;https://github.com/riscv/sail-riscv/pull/608 使得sail-riscv可以设置计算vl的方法（ceil或者直接取vlmax） \
&emsp;https://github.com/riscv/sail-riscv/pull/558 zvbb扩展 \
&emsp;https://github.com/riscv/sail-riscv/pull/550 zvbc扩展 \
&emsp;zcmp扩展在做

