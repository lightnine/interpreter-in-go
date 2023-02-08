# interpreter-in-go
use the glang to writing an interpreter （来自：https://book.douban.com/subject/27034273/）

采用golang开发一款interpreter，用来执行monkey编程语言(自己定义的编程语言)。monkey支持变量定义，if条件，内置整型、字符串、数组、hash等类型。当然有些语句不支持，比如for循环等。整体的开发过程是采用TDD方法论来进行的。

interpreter主要包括三块内容，分别为：
lexer(词法分析)：将source code解析为token，使得parser阶段更加容易
parser：将token输入解析为ast数据结构，ast数据结构是一个树。完整的表示了source code。
evaluator：将ast输入进行评估，得到结果
一般interpreter就包括这三块，当然有些为了效率上的提升，还有有IR代码等中间表示

## code of conduct
token： 包含token定义，比如monkey中的关键字let、true、false、string、fn等
lexer：将source code解析为一个一个的token
ast：定义ast结构，最重要的是定义树中的node节点类型，比如LetStatment、Expression等。这里涉及到要将monkey中的内容进行抽象考虑。
parser：将token解析成ast结构，成为一颗树
object：定义评估阶段需要的数据结构
evaluator：输入ast，执行评估，获取结果
repl：能够进行read-evaluate-print-loop

