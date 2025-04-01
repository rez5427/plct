https://github.com/chipsalliance/rvdecoderdb/pull/39 \
重新写sail-riscv,使用rvdecoderdb和每个扩展指令的实现生成rv_model \
sail-riscv作为一个riscv的formal实现应该很好做验证，但是现在的sail-riscv有很多缺点 \
  1 比如对各种指令的实现函数封装很多，使用者不能像读riscv spec一样很清晰的看出这个指令的逻辑。 \
  2 不支持对用户自定义指令，扩展，自定义实现的支持 \
  3 不支持用户对csr每一位外部设定，例如mip这个csr，当中断到达的时候应该由rv_model外部设置该寄存器 \
  4 很难通过rvfi来对外部实现做精细difftest \

然后在这个基础上，实现的sailcodegen，由rvdecoderdb提供指令编码信息，手写riscv指令的sail实现，然后手写对csr的每一位定义, 加上设计好的rv_model对外暴露的capi生成rv_model \
目前对这个是采取对rv_model，sail，gmp，zlib打包成artifact然后在rust链接所有，在rust提供main函数执行。

下面是之前sail-riscv的工作（这个月已合并） \
https://github.com/riscv/sail-riscv/pull/550/   zvbc扩展 \
https://github.com/riscv/sail-riscv/pull/790    zvbb zvkb扩展 \
