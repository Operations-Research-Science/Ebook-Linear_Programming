# 第7章 优化求解器及其比较

作者：魏晓阳 新加坡国立大学 土木与环境工程系 博士生在读

# 1. 优化求解器

## 1.1. AIMMS

AIMMS（Advanced Integrated Multidimensional Modeling System，
高级交互式多维建模系统）有两个主要产品，可提供跨多个行业的建模和优化功能：(1)
AIMMS规范分析平台允许高级用户开发基于优化的应用程序并将其部署到业务用户；(2)
AIMMS SC
Navigator基于AIMMS规范分析平台构建，为供应链团队提供可配置的应用程序，为非高级用户提供了供应链分析。AIMMS旨在建模和解决大规模优化和调度问题，被认为是五种最重要的代数建模语言之一，该软件获得了INFORMS影响力奖。

AIMMS规范分析平台包括代数建模语言，用于编辑模型和围绕这些模型创建图形用户界面的集成开发环境，以及图形最终用户环境。随着对用于供应链管理的嵌入式高级分析的兴趣日益浓厚，AIMSS开发了AIMMS
SC
Navigator平台以支持供应链分析，最初使用三个基于云的应用程序：供应链网络设计、销售和运营计划以及数据导航器。

AIMMS通过AIMMS开放求解器接口链接到多个求解器。支持的求解器包括CPLEX、MOSEK、FICO
Xpress、CBC、Conopt、MINOS、IPOPT、SNOPT、KNITRO和CP Optimizer。

AIMMS具有声明式和命令式programming风格的混合体。优化模型的制定是通过声明性语言元素（例如集合和索引，以及标量和多维参数，变量和约束）进行的，这些元素对于所有代数建模语言都是通用的，并且可以简要描述大多数问题的数学优化。语言本身就支持度量单位，并且可以使用编译和运行时单位分析来检测建模错误。为了支持通用建模组件的重用，AIMMS允许建模人员在用户模型库中组织其模型。AIMMS支持多种数学优化问题类型：

(1) 线性规划

(2) 二次规划

(3) 非线性规划

(4) 混合整数规划

(5) 混合整数非线性规划

(6) 全局优化互补问题（MPEC）

(7) 随机规划

(8) 鲁棒优化

(9) 约束规划

通过指定其他属性，可以在AIMMS中的确定性线性和混合整数优化模型中考虑不确定性，从而可以将随机性或鲁棒性优化技术与现有的确定性解决方案技术一起使用。可以使用GMP系统库构建自定义的混合算法和分解算法，该库在建模级别提供AIMMS中存在的高级解决方案方法，矩阵修改方法以及用于自定义解决方案的特定问题类型的算法。用AIMMS创建的优化解决方案既可以用作独立的桌面应用程序，也可以作为软件组件嵌入其他应用程序中。

## 1.2. ALGLIB

ALGLIB是一个跨平台的开源数值分析和数据处理库。可以通过多种编程语言（C
++、C＃、VB.NET、Python、Delphi）调用它。它被多个开源项目、商业库和应用程序使用（例如TOL项目、Math.NET
Numerics、SpaceClaim）。该库的独特功能是：

(1) 支持具有相同API的多种编程语言（C ++、C＃、FreePascal /
Delphi、VB.NET和Python）

(2) 自包含代码，没有强制性的外部依赖关系，易于安装

(3) 可移植性（已在x86 / x86-64 / ARM、Windows和Linux下进行了测试）

(4) 两个独立的后端（纯C＃实现、本机C实现）和自动生成的API（C ++、C＃等）

(5) 商业版和GPL版具有相同的功能

ALGLIB提供以下功能：

(1) 线性代数（直接算法、求解器、EVD / SVD）

(2) 快速傅里叶变换

(3) 数值积分

(4) 插值

(5) 线性和非线性最小二乘拟合

(6) 优化

(7) 常微分方程

(8) 统计（描述性统计、假设检验）

(9) 数据分析（分类/回归，包括神经网络）

(10) 线性代数、插值和优化算法的多种精度版本（使用MPFR进行浮点计算）

## 1.3. AMPL

数学编程语言（AMPL）是一种代数建模语言，用于描述和解决大规模数学计算的高复杂性问题（即大规模优化和调度问题）。它是由Bell实验室的Robert
Fourer、David Gay和Brian Kernighan开发的。
AMPL支持许多求解器，包括CBC、CPLEX、FortMP、Gurobi、MINOS、IPOPT、SNOPT、KNITRO和LGO。问题以nl文件的形式传递给求解器。

AMPL的优点之一是其语法与优化问题的数学符号相似。这允许在优化领域中对问题进行非常简明易懂的定义。
NEOS服务器（以前由Argonne国家实验室托管，目前由威斯康星大学麦迪逊分校托管）上可用的许多现代求解器都接受AMPL输入。根据NEOS统计，AMPL是表示数学编程问题的最流行格式。AMPL混合了声明式和命令式编程样式。建立优化模型是通过声明性语言元素（例如集合、标量、多维参数、决策变量、目标和约束条件）进行的，从而可以对数学优化领域中的大多数问题进行简洁的描述。为了支持重用并简化大规模优化问题的构建，AMPL允许模型和数据分离。
AMPL支持多种问题类型，其中包括：

(1) 线性规划

(2) 二次规划

(3) 非线性规划

(4) 混合整数规划

(5) 具有或不具有凸二次约束的混合整数二次规划

(6) 混合整数

(7) 非线性规划

(8) 二阶锥规划全局优化

(9) 具有双线性矩阵不等式的半定规划问题

(10) 离散或连续变量的互补理论问题（MPEC）

(11) 约束规划

## 1.4. [ANTIGONE](https://en.wikipedia.org/wiki/ANTIGONE)

ANTIGONE（Algorithms for coNTinuous / Integer Global Optimization of Nonlinear
Equations）是混合整数非线性程序（MINLP）的确定性全局优化求解器。ANTIGONE是GlomiQO的演进，它是Ruth
Misener编写的全局混合整数二次规划求解器。
ANTIGONE将GloMIQO的功能扩展到了一般的MINLP问题。

像所有确定性全局优化软件一样，ANTIGONE是许多技术的工具箱，用于处理非线性结构的不同特殊情况。话虽如此，它主要是分支定界求解器。它的主要算法过程分为4个主要步骤：

(1) 用户输入的重新形成

(2) 特殊结构的检测

(3) 为检测到的结构选择最佳算法

(4) 使用所选算法解决问题

除了特殊情况下的优化问题（例如凸NLP）可以在分支定界算法的根节点处求解，ANTIGONE将启动分支定界过程。此过程包括以下步骤：

(1) 生成/更新凸松弛（下界问题）

(2) 域约简

(3) 搜索可行的解决方案（上限）

(4) 通过解决凸下界问题来计算严格的下界

ANTIGONE采用经典的可分解programming技术来生成relaxation（例如McCormick
relaxation），以及重新线性化技术（RLT）、边缘凸/凹relaxation和Alpha BB切割。
ANTIGONE还拥有一个动态剪切生成器，它可以生成并处理本地和全局有效剪切。

像所有确定性全局优化软件一样，ANTIGONE要求用户为问题中使用的所有函数提供明确的数学表达式，以及所有变量的初始边界。如果未提供初始界限，则ANTIGONE将尝试推断界限，但不能保证全局最优性。
ANTIGONE只能解决微分函数，不能解决三角问题。ANTIGONE是GAMS建模平台的一部分。

## 1.5. APMonitor

高级过程监控器（APMonitor）是一种用于微分代数（DAE）方程的建模语言。它是一个免费的Web服务或本地服务器，用于以隐式DAE模型的形式求解物理系统的表示形式。
APMonitor适用于大规模问题，可解决线性规划、整数规划、非线性规划、非线性混合整数规划、动态仿真、动视域估计和非线性模型预测控制。APMonitor不能直接解决问题，而是调用非线性规划求解器，例如APOPT、BPOPT、IPOPT、MINOS和SNOPT。
APMonitor
API通过自动微分和稀疏矩阵形式为求解器提供连续函数的精确一阶和二阶导数。

Julia、MATLAB和Python等编程语言，通过Web服务API集成了APMonitor。
GEKKO优化套件是APMonitor的最新扩展，具有完整的Python集成。这些接口是内置的优化工具箱或模块，用于加载和处理优化问题的解决方案。
APMonitor是一种面向对象的建模语言和优化套件，它依赖于编程语言来加载、运行和检索解决方案。
APMonitor模型和数据在运行时进行编译，并转换为对象，这些对象由优化引擎（例如APOPT或IPOPT）解决。
APMonitor未指定优化引擎，因此可以切换多种不同的优化引擎。还可以配置仿真或优化模式，以重新配置模型、进行动态仿真、非线性模型预测控制、移动视界估计或数学优化中的一般问题。

## 1.6. APOPT

APOPT（Advanced Process
OPTimizer）是用于解决以下任意形式的大规模优化问题的软件包：

(1) 线性规划（LP）

(2) 二次规划（QP）

(3) 二次约束二次规划（QCQP）

(4) 非线性规划（NLP）

(5) 混合整数规划（ MIP）

(6) 混合整数线性规划（MILP）

(7) 混合整数非线性规划（MINLP）

APOPT的应用包括化学反应器、摩擦搅拌焊接、防止深海管道中水合物的形成、计算生物学、固体氧化物燃料电池和无人飞行器（UAV）的飞行控制。

## 1.7. Artelys Knitro

Artelys Knitro 是用于解决大规模非线性数学优化问题的商业软件包。 KNITRO由Richard
Waltz、Jorge Nocedal、Todd Plantenga和Richard
Byrd共同创建。它于2001年作为美国西北大学学术研究的衍生产品（通过Ziena
Optimization LLC）首次引入，此后一直由Artelys的开发人员不断改进。

优化问题必须以数学形式呈现给Knitro，并应提供一种使用稀疏矩阵计算函数导数的方式（Knitro可以计算导数近似值，但在大多数情况下，提供精确的导数是对求解有帮助的）。通常更容易的方法是用代数建模语言搭建优化问题。Knitro专门从事非线性优化，但也解决了一系列优化问题：

(1) 一般非线性问题（NLP），包括非凸问题

(2) 非线性方程组

(3) 线性问题（LP）

(4) 凸和非凸二次问题（QP / QCQP / SOCP）

(5) 最小二乘问题/线性和非线性回归

(6) 具有互补性约束的数学程序（MPCC / MPEC）

(7) 混合整数非线性问题（MIP / MINLP）

(8) 无导数优化问题（DFO）

Artelys Knitro包含多种优化算法：

(1)
非线性规划（NLP）求解器。Knitro提供了四种不同的优化算法来解决优化问题。两种算法属于内部点类型，两种算法属于活动集（active
set）类型。众所周知，这些算法具有根本不同的特征。例如，内部点方法沿着通过可行区域内部的路径行进，而活动集（active
set）方法往往停留在边界处。
Knitro可以在求解过程中从一种算法转换为另一种算法。该代码还提供了一个多启动选项，以促进全局最小值的计算。

(i) 内部/直接算法

(ii) 内部/共轭梯度算法

(iii) 活动集（active set）算法

(iv) 顺序二次规划（SQP）算法

(2)
混合整数非线性规划（MINLP）求解器。Knitro提供了用于求解具有二进制或整数变量的优化模型（线性和非线性）的工具。
Knitro混合整数规划（MIP）代码为混合整数非线性规划（MINLP）提供了三种算法：

(i) 非线性分支和边界

(ii) Quesada Grossman算法

(iii) 混合整数顺序二次规划（MISQP）

Artelys Knitro支持多种编程和建模语言，包括：

(1) 适用于C ++、C＃、Java和Python的面向对象的接口

(2) 适用于C、Fortran、MATLAB和R的面向矩阵的接口

(3) 链接到建模语言AIMMS、AMPL、GAMS和MPL

(4) 通过Frontline Solvers链接到Excel

Artelys Knitro还包括许多关键功能：

(1) 大量用户选项和自动调谐器

(2) （并行）全局优化的多起点

(3) 导数近似和校验器

(4) 内部预解析器

## 1.8. Cassowary

Cassowary是一个增量约束解决工具包，可以有效地解决线性等式和不等式的系统。约束可以是要求，也可以是首选项。客户代码指定要维护的约束，求解器将约束变量更新为具有满足约束的值。

Cassowary由Greg Badros、Alan Borning和Peter J.
Stuckey开发，并针对用户界面应用进行了优化。Badros还使用Cassowary来实现约束层叠样式表（CCSS），这是层叠样式表（CSS）的扩展。CCSS添加了对布局约束的支持。这些使设计人员可以更灵活地描述网页的布局。Cassowary用于解决这些限制并计算最终布局。

主版本中提供Smalltalk、C ++和Java版本。此外，还有GNU
Guile、Python和STk的绑定。其他人已将求解器移植到JavaScript、Dart、Squeak、Python、.NET框架（Cassowary.net）和Rust。

## 1.9. COIN-OR

Computational Infrastructure for Operations Research（COIN-OR）是一个旨在“create
for mathematical software what the open literature is for mathematical
theory”。开放文献（例如研究期刊）为运筹学（OR）社区提供了同行评审过程和存档。运筹学期刊上有关数学理论的论文通常包含支持计算研究的数值结果。通常不会发布用于产生数值结果的软件实现，模型和数据。这一现状阻碍了研究人员重现计算结果，进行公平的比较并扩展了现有技术水平。
COIN-OR被认为是一项计划，目的是在计算运筹研究社区中推广开源软件，并提供使其他人能够运行自己的开源软件项目所需的在线资源和托管服务。

COIN-OR网站是与2000年在佐治亚州亚特兰大举行的第17届国际数学编程专题讨论会一起启动。在2007年，COIN-OR拥有25个应用项目，包括用于线性规划（例如COIN-OR
CLP）、非线性规划（例如IPOPT）、整数规划（例如CBC、Bcp和COIN-OR
SYMPHONY）的工具、代数建模语言（例如Coopr）等。到2011年，该项目已发展到48个项目。COIN-OR由INFORMS运筹学与管理科学研究所主办，由教育性、非营利性COIN-OR基金会运营。

在AIMMS、AMPL和GAMS建模系统以及FortSP求解器中都可以使用COIN-OR求解器。也可以通过OpenSolver和SolverStudio加载项在Excel中使用它们。

## 1.10. [CPLEX](https://en.wikipedia.org/wiki/CPLEX)

IBM ILOG CPLEX Optimization Studio（CPLEX）是一个优化软件包。
2004年，CPLEX的工作获得了首届INFORMS影响力奖。CPLEX
Optimizer以使用C编程语言实现的单纯形方法而命名，尽管今天它还支持其他类型的数学优化并提供除C之外的接口。它最初由Robert
E.
Bixby开发，并于1988年由CPLEX商业出售，随后ILOG在2009年1月被IBM收购。IBM继续积极开发CPLEX。

IBM ILOG CPLEX
Optimizer解决了整数规划问题、非常大的线性规划问题、凸和非凸二次规划问题以及凸二次约束问题（通过二阶锥规划或SOCP求解）。
CPLEX Optimizer具有一个称为Concert的建模层，该层提供了与C
++、C＃和Java语言的接口，有一个基于C接口的Python语言接口。此外，还提供了Microsoft
Excel和MATLAB的连接器。最后，提供了一个独立的Interactive
Optimizer可执行文件，用于调试和其他目的。

可通过独立的建模系统（例如AIMMS、AMPL、GAMS、OptimJ和TOMLAB）访问CPLEX
Optimizer。除此以外，AMPL还提供了CPLEX CP Optimizer的接口。完整的IBM ILOG CPLEX
Optimization Studio包括用于数学规划的CPLEX Optimizer、用于约束规划的CP
Optimizer、优化编程语言（OPL）和集成的IDE。

## 1.11. FICO Xpress

FICO
Xpress优化器用于线性规划（LP）、混合整数线性规划（MILP）、凸二次规划（QP）、凸二次约束二次规划（QCQP）、二阶锥规划（SOCP）等。Xpress包括通用非线性求解器Xpress
NonLinear，其中包括连续线性规划算法（一阶方法）和Artelys Knitro（二阶方法）。

Xpress最初由Dash
Optimization开发，并于2008年被FICO收购。它的最初作者是鲍勃·丹尼尔（Bob
Daniel）和罗伯特·阿什福德（Robert Ashford）。
Xpress是第一个通过在2010年引入64位索引来突破十亿决策变量阈值的MIP解决方案。自2014年以来，Xpress首次采用并行对偶单纯形法的商业实现。

线性和二次程序可以通过原始单纯形法、对偶单纯形法或barrier interior point
求解。所有混合整数规划变量都通过分支定界方法和切面方法的组合来求解。可以通过IIS（Irreducible
Infeasible Subset）方法分析不可行的问题。
Xpress提供了一个内置的调谐器，用于自动调整控制设置。Xpress包括其建模语言Xpress
Mosel和集成开发环境Xpress Workbench。
Mosel包括分布式计算功能，因此可以并行解决优化问题的多种情况。

Xpress具有一个称为BCL（Builder Component Library）的建模模块，该模块可与C、C
++、Java编程语言和.NET框架接口。独立于BCL，有Python和MATLAB接口。
Xpress还可以连接到其他标准建模语言，例如AIMMS、AMPL和GAMS。FICO Xpress
Executor使用SOAP或REST接口执行和部署Mosel模型。可以从外部应用程序或FICO Decision
Management Platform使用它。

## 1.12. [FortMP](https://en.wikipedia.org/wiki/FortMP)

FortMP是用于解决大规模优化问题的软件包。它解决了线性规划问题、二次规划问题和混合整数规划问题（线性和二次）。它的鲁棒性已经被探索并发表在《Mathematical
Programming》上。

FortMP可以作为独立的可执行文件接受MPS格式的输入，也可以作为具有C和Fortran接口的库提供。
AMPL建模系统也支持它。FortMP中实现的主要算法是使用稀疏矩阵的原始和对偶单纯形算法。通过内点法对大型问题和二次规划问题进行了补充。使用分支定界算法解决混合整数规划问题。

## 1.13. Gekko

GEKKO
Python软件包使用非线性规划求解器（IPOPT、APOPT、BPOPT、SNOPT和MINOS）求解大型混合整数和微分代数方程。操作模式包括机器学习、数据协调、实时优化、动态仿真和非线性模型预测控制。此外，该软件包还解决了线性规划（LP）、二次规划（QP）、二次约束二次规划（QCQP）、非线性规划（NLP）、混合整数规划（MIP）和混合整数线性规划（MILP）的问题。

GEKKO可以被Python中调用。默认情况下，问题将发送到公共服务器，在该服务器上计算解决方案并将其返回给Python。可以在Windows、MacOS、Linux和ARM（Raspberry
Pi）平台上运行。 GEKKO是APMonitor Optimization
Suite的扩展，但已将建模和解决方案可视化，直接集成在Python中。

应用包括热电联产（电力和热力）、钻探自动化、严格的炉渣控制、太阳能项目、固体氧化物燃料电池、流量保证、提高采油率、提取精油和无人飞行器（UAV）。GEKKO是由美国国家科学基金会（NSF）的研究资助开发的，在有关联合调度与控制的特刊中有详细介绍。

## 1.14. [GLPK/GLPSOL](https://en.wikipedia.org/wiki/GNU_Linear_Programming_Kit)

GNU Linear Programming
Kit（GLPK）是一个软件包，用于解决大规模线性规划（LP）、混合整数规划（MIP）和其他相关问题。它是一组用ANSI
C编写并以可调用库的形式组织的例程。该软件包是GNU项目的一部分，并根据GNU通用公共许可证发行。

可以使用GNU
MathProg语言（以前称为GMPL）对问题进行建模，该语言与AMPL共享大多数语法，并使用独立的求解器GLPSOL进行解决。GLPK也可以用作C库。

GLPK对非整数问题使用修订的单纯形法和原始对偶内点法，并将分支定界算法与Gomory的混合整数割对（混合）整数问题结合使用。免费版的OptimJ建模系统支持GLPK，这允许Java应用程序以相对透明的方式调出GLPK。GLPK由莫斯科航空学院的Andrew
O. Makhorin开发，首次公开发布于2000年10月。

## 1.15. GNU Scientific Library

GNU Scientific Library（GSL）是一个用于在应用数学和科学中进行数值计算的软件库。
GSL用C编写。 GSL是GNU Project的一部分，并根据GNU通用公共许可证进行分发。

GSL项目由洛斯阿拉莫斯国家实验室的物理学家Mark Galassi和James
Theiler于1996年发起。他们的目的是为广泛使用但有些过时的Fortran库（例如Netlib）编写一个现代的替代品。他们进行了总体设计并编写了早期模块。

由于GSL是用C编写的，因此很容易为其他编程语言提供wrapper。这些wrapper目前存在于：

(1) AMP

(2) C++

(3) Fortran

(4) Haskell

(5) Java

(6) Lisp

(7) Ocaml

(8) Octave

(9) Perl Data Language

(10) Python

(11) R

(12) Ruby

## 1.16. [Gurobi](https://en.wikipedia.org/wiki/Gurobi)

Gurobi
Optimizer是用于线性规划（LP）、二次规划（QP）、二次约束规划（QCP）、混合整数线性规划（MILP）、混合整数二次规划（MIQP）和混合整数二次规划（MIQCP）的商业优化求解器。

Gurobi成立于2008年，以其创始人命名：Zonghao **Gu**、Edward **Ro**thberg和Robert
**Bi**xby。
Bixby还是CPLEX的创始人，而Rothberg和Gu领导CPLEX开发团队近十年。Gurobi
Optimizer支持多种编程和建模语言，包括：

(1) C ++、Java、.NET和Python的面向对象接口

(2) 适用于C、MATLAB和R的面向矩阵接口

(3) 可以链接到标准建模语言AIMMS、AMPL、GAMS和MPL

(4) 通过其分析求解器和求解器SDK产品链接到Excel

Gurobi Optimizer还包括许多功能来支持优化模型的构建，其中包括：

(1) 可以灵活确定多个目标的优先级

(2) 诸如MIN / MAX、ABS、AND / OR之类的常规约束以及指标约束

(3) 具有凸、分段线性目标函数的模型用于描述某些非线性问题

(4) 任意分段线性目标函数

(5) 分布式调参，以加快参数设置的探索速度，加快求解时间

Gurobi Optimizer还可以部署在云上，以及用于服务器-客户端模式。

## 1.17. IMSL Numerical Libraries

IMSL Numerical
Libraries是商业上具有数字分析功能的软件库，这些软件库以计算机编程语言C、Java、C＃.NET和Fortran实现，也提供Python界面。IMSL库由Rogue
Wave Software提供。

第一个针对Fortran语言的IMSL库于1970年发布，随后是1991年最初称为C /
Base的C语言版本，2002年的Java语言版本和2004年的C＃语言版本。最近的一些发行版都涉及Python提供IMSL库函数。PyIMSLwrapper程序于2008年8月首次发布。PyIMSL
Studio在2009年2月推出。PyIMSLStudio可免费下载用于非商业用途或用于商业评估。各种操作系统\\硬件和编译器均支持IMSL
Numerical Libraries。

## 1.18. [LINDO](https://en.wikipedia.org/wiki/LINDO)

LINDO（Linear, Interactive, and Discrete
Optimizer）是用于线性规划、整数规划、非线性规划、随机规划和全局优化的软件包。

Lindo还创建了“ What'sBest！”，是一种线性、整数和非线性优化的插件。最初针对Lotus
1-2-3发布，后来也针对Microsoft Excel发布。

## 1.19. LIONsolver

LIONsolver（Learning and Intelligent
OptimizatioN）是用于数据挖掘、商业智能、分析和建模的集成软件。非营利版本为LIONoso。LIONsolver可用于构建模型、可视化模型并改善业务和工程流程。它是基于数据和定量模型进行决策的工具，可以连接到大多数数据库和外部程序，并且与Grapheur商业智能软件完全集成，并且适合对设计业务逻辑和流程感兴趣的高级用户使用。

LIONsolver源自反应式搜索优化中的研究原理，该论点主张在软件系统运行时使用自调整方案。学习和智能优化是指将在线机器学习方案集成到优化软件中，从而使其能够从以前的运行和人工反馈中学习。它提供了一种定义设计空间的直接方法，其中涉及反应式搜索优化，而“自主搜索”则提倡采用自适应问题解决算法。建模组件包括神经网络、多项式、局部加权贝叶斯回归、k均值聚类和自组织图。提供了用于非商业用途和课堂使用的免费学术许可证。

LIONsolver的软件体系结构允许交互式和多目标优化，其用户界面可直观显示结果并促进解决方案分析和决策过程。该体系结构允许针对特定问题进行扩展，并且它可作为具有多种不同潜在解决方案的所有优化方案的后处理工具。当架构与特定的问题解决或优化方法紧密耦合时，可以开发有效的交互方案。

## 1.20. Math Kernel Library

Intel Math Kernel Library (Intel MKL)
是针对科学、工程和金融应用程序优化的数学例程的库。核心数学功能包括BLAS、LAPACK、ScaLAPACK、稀疏求解器、快速傅立叶变换和矢量数学。MKL中的例程专门针对Intel处理器进行了优化。该库支持Intel处理器，可用于Windows、Linux和macOS操作系统。

英特尔C
++编译器生成的英特尔MKL和其他程序使用一种称为函数多版本化的技术来提高性能。英特尔MKL具有以下功能类别：

(1) 线性代数

(2) 快速傅立叶变换（FFT）

(3) 向量数学

(4) 统计

(5) 数据拟合

(6) 深度神经网络

(7) 偏微分方程

(8) 非线性优化问题求解器

## 1.21. MathCad

MathCad是一种交互式数值计算系统。当输入一个数学公式、方程组、矩阵等，计算机将直接给出计算结果，而无须去考虑中间计算过程。因而MathCad在航空、国防、消费品设计等科学和工程领域中承担着复杂的数学计算、图形显示和文档处理，是工程技术人员常用的工具。Mathcad有五个扩展库，分别是求解与优化、数据分析、信号处理、图像处理和小波分析。

Mathcad采用接近在黑板上写公式的方式让用户表述所要求解的问题，通过底层引擎计算返回结果并显示在屏幕上。计算过程近似透明，使用户专注于对问题的思考而不是繁琐的求解步骤。

经过20年发展，Mathcad从早期的简单有限功能发展到现在的代数运算、线性及非线性方程求解与优化、常微分方程、偏微分方程、统计、金融、信号处理、图像处理等许多方面。并提供丰富的接口可以调用第三方软件的功能，利于自行扩展和利用别的软件扩展功能。Mathcad集programming、计算、显示、文档记录于一体，是美国PTC公司的产品。

## 1.22. [Mathematica](https://en.wikipedia.org/wiki/Mathematica)

Wolfram
Mathematica（通常称为Mathematica）是一个现代技术计算系统，涵盖了技术计算的大多数领域，包括神经网络、机器学习、图像处理、几何、数据科学、可视化等。该系统用于许多技术、科学、工程、数学和计算领域。它由斯蒂芬·沃尔夫拉姆（Stephen
Wolfram）构思，并由伊利诺伊州尚佩恩的沃尔夫拉姆研究中心（Wolfram
Research）开发。Wolfram语言是Mathematica中使用的编程语言。

Wolfram
Mathematica分为内核和前端两部分。内核解释表达式（Wolfram语言代码）并返回结果表达式。前端由Theodore
Gray在1988年设计，提供了一个GUI，它允许创建和编辑Notebook文档，其中包含带有语法突出显示的程序代码、格式化的文本、结果、表格和声音。所有内容和格式都可以通过算法生成或进行交互式编辑。支持标准的文字处理功能，包括实时的多语言拼写检查。

可以使用单元的层次结构来结构化文档，从而可以对文档进行概述和分段，并支持自动编号索引的创建。笔记本及其内容以Mathematica表达式表示，可以由Mathematica程序创建、修改或分析，也可以转换为其他格式。演示者工具支持创建幻灯片样式的演示文稿，该演示文稿支持演示过程中的交互元素和代码执行。

Wolfram Workbench是可供选择的前端之一，Wolfram
Workbench是基于Eclipse的集成开发环境（IDE），于2006年推出。它为Mathematica提供基于项目的代码开发工具，包括修订管理、调试、配置文件和测试。有一个基于IntelliJ
IDEA的IDE可以与Wolfram语言代码一起使用的插件，该插件除了语法高亮显示之外还可以分析和自动完成局部变量和定义的函数。Mathematica内核还包括命令行前端，其他接口包括基于GNU
readline的JMath 和从UNIX命令行运行的WolframScript。

以下方法可以部署用Wolfram Mathematica编写的应用程序：

(1) Mathematica Player
Pro是Mathematica的运行时版本，它将运行任何Mathematica应用程序，但不允许编辑或创建代码。

(2) 提供了免费版本Wolfram CDF
Player，用于运行以可计算文档格式（CDF）保存的Mathematica程序。它也可以查看标准Mathematica文件，但不能运行它们。它包括适用于Windows和Macintosh上常见Web浏览器的插件。

(3)
webMathematica允许Web浏览器充当远程Mathematica服务器的前端。它旨在允许通过任何平台上的浏览器远程访问用户编写的应用程序。它可能无法用于完全访问Mathematica。由于带宽限制，Web浏览器不完全支持交互式3D图形。

(4) Wolfram语言代码可以转换为C代码或自动生成的DLL。

(5) Wolfram语言代码Web应用程序或API在Wolfram托管的服务器上或Wolfram Enterprise
Private Cloud的私有安装中运行。

## 1.23. MIDACO

MIDACO（Mixed Integer Distributed Ant Colony
Optimization）是用于基于进化计算的数值优化的软件包。 MIDACO是与欧洲航天局和EADS
Astrium合作创建的，旨在解决受限的混合整数非线性（MINLP）空间应用。MIDACO拥有欧洲航天局公开提供的关于行星际航天轨迹设计问题的几种记录解决方案。
MIDACO包含在以下软件包中：TOMLAB、Astos和SigmaXL等。

## 1.24. [MINOS](https://en.wikipedia.org/wiki/MINOS_(optimization_software))

MINOS是用于解决线性和非线性数学优化问题的Fortran软件包。
MINOS（可用于线性规划、二次规划以及更通用的目标函数和约束条件，以及为一组线性或非线性等式和不等式寻找可行点。

MINOS由Bruce Murtagh和Michael
Saunders首先开发，主要是由斯坦福大学运筹学系的系统优化实验室开发。1985年，桑德斯（Saunders）因在MINOS上的工作而被数学规划协会（现为数学优化协会）授予了首届Orchard-Hays奖。它是最先出现的通用约束优化求解器之一，现在仍在大量使用。
MINOS在AIMMS、AMPL、APMonitor、GAMS和TOMLAB建模系统中受支持。此外，它仍然是NEOS
Server和GAMS中使用次数最多的求解器之一。

理想情况下，用户应提供非线性函数的梯度。如果未提供某些或全部梯度，则MINOS将通过有限的差值来近似缺少的梯度，但这可能会很慢且可靠性较低。如果目标函数是凸的且约束是线性的，则获得的解将是全局极小值。否则，获得的解决方案可能是局部最小值。

对于线性程序，使用两阶段原始单纯形法。第一阶段将不可能性的总和最小化。对于具有线性约束和非线性目标的问题，使用减小梯度法。保持对简化的Hessian的拟牛顿近似，以获得搜索方向。当在解决方案上有许多约束或界限处于活动状态时，该方法最有效。对于具有非线性约束的问题，使用了线性约束拉格朗日方法。这涉及一系列主要迭代，每个迭代都（近似）解决一个线性约束子问题。子问题目标是扩充的拉格朗日，而子问题约束是当前点处非线性约束的线性化。MINOS旨在解决大型稀疏问题，问题大小没有固定的限制。源代码适用于所有具有Fortran编译器的科学机器。

## 1.25. [MINTO](https://en.wikipedia.org/wiki/MINTO)

MINTO（Mixed Integer
Optimizer）是使用分支定界算法的整数规划求解器。MINTO是一个软件系统，它通过具有线性规划松弛的分支定界算法来解决混合整数规划问题。它还提供自动约束分类、预处理、原始启发式和约束生成。它还具有内置的剪切生成，可以创建背包剪切、GUB剪切、集团剪切、隐含剪切、流剪切、混合整数舍入和Gomory剪切。此外，用户可以通过提供各种可以定制MINTO的专用例程来丰富基本算法，以提高问题求解的效率。

MINTO本身没有线性规划（LP）求解器。它可以通过COIN-OR的OSI接口使用大多数LP求解器，例如CLP、CPLEX、XPRESS。它可以在Linux和Windows操作系统上运行，
MINTO是一种非商业解决方案，其可执行文件可以从其主页COR \@ L免费下载。

## 1.26. [MOSEK](https://en.wikipedia.org/wiki/MOSEK)

MOSEK是用于解决线性、混合整数线性、二次、混合整数二次、二次约束、圆锥和凸非线性数学优化问题的软件包。
MOSEK的重点是解决大规模稀疏问题，尤其是线性，圆锥二次（又称二阶锥规划）和半定（即半定规划）的内点优化器。该软件特别有效地解决了后一类问题。MOSEK内部点优化器的一个特殊功能是它基于所谓的均质模型。这意味着MOSEK可以可靠地检测到原始和/或双重不可行状态。

该软件由丹麦公司Mosek ApS开发，该公司由Erling D.
Andersen于1997年成立。除了内部点优化器之外，MOSEK还包括：

(1) 线性问题的原始和对偶单纯形优化器

(2) 线性、二次和圆锥问题的混合整数优化器

在版本9中，Mosek在其求解器中引入了对指数锥和幂锥的支持。该软件还提供与C、C＃、Java和Python语言的接口。大多数主要的建模系统都与MOSEK兼容，例如AMPL和GAMS。
MOSEK也可以从诸如MATLAB和R编程语言/软件环境之类的流行工具中使用。

## 1.27. NAG Numerical Library

NAG Numerical
Library是由数值算法组开发和销售的软件产品。它是一个数值分析例程的软件库，其中包含1900多种数学和统计算法。该库涵盖的领域包括线性​​代数、优化、正交、常微分方程、偏微分方程、回归分析和时间序列分析。

NAG库的用户可以从其应用程序中调用其例程，以合并其数学或统计功能并解决数值问题，例如，找到函数的最小值或最大值、将曲线或曲面拟合到数据、求解微分方程。该库有多种形式，分别是NAG
C库、NAG
Fortran库和用于.NET的NAG库。可从几种计算环境访问其内容，包括标准语言（例如C、C
++、Fortran、Visual
Basic、Java、Python和C＃）以及软件包（例如MATLAB、R、LabVIEW、Excel、Origin和Ch）。支持的操作系统包括Windows、Linux和macOS，以及Solaris、AIX和HP-UX。

## 1.28. NMath

NMath是Microsoft .NET Framework的数值程序包。它由CenterSpace
Software开发，基于MKL（英特尔的数字库）构建。

NMath包含矢量和矩阵类、复数、分解、线性规划、最小化、求根、结构化、稀疏矩阵、最小二乘、多项式、模拟退火、曲线拟合、数值积分和微分等。

## 1.29. [Octeract Engine](https://en.wikipedia.org/wiki/Octeract_Engine)

Octeract
Engine是专有的大规模、并行、确定性、全局优化求解器，适用于一般的混合整数非线性程序（MINLP）。它使用MPI作为加速求解时间的一种方式。Octeract
Engine的第一个公开测试版于2019年8月发布。截至2019年12月，该引擎仍处于beta版。Octeract
Engine是一个符号分支定界求解器。它是目前唯一支持超级计算的确定性全局优化软件。它的一些功能是：

(1) 通过MPI进行分布式计算

(2) 支持不连续的基本功能（例如最小和最大）

(3) 支持三角函数

(4) 保证全局最优

(5) 重新编写用户输入

(6) 检测特殊结构

(7) 通过区间算术和任意精度算术保证计算

(8) 基于Python的界面称为Octeract Shell

像所有确定性全局优化软件一样，Octeract
Engine需要针对问题中使用的所有函数使用明确的数学表达式。Octeract
Engine可以直接运行，也可以在C
++和Python中作为库调用。它支持以下建模语言：AMPL、ASL、GAMS、Pyomo。该引擎还具有用于以下求解器的接口：Gurobi、CBC、CLP、IPOPT、NLOPT、BONMIN。

## 1.30. OptaPlanner

OptaPlanner是用Java编写的开放源代码约束求解器。它通过构造启发式算法和元启发式算法解决了约束满足问题。OptaPlanner由Red
Hat赞助，后者是JBoss社区的一部分，并且与KIE集团的Drools和jBPM项目密切相关。

它由Geoffrey De
Smet于2006年以Taseree的名义创立。2013年3月，更名为OptaPlanner。它由一个专门的核心团队（由Red
Hat雇用）和外部社区贡献者进行持续开发。Red Hat针对OptaPlanner的支持产品称为Red
Hat业务优化器（在2018年之前称为Red Hat
JBoss业务资源规划器）。OptaPlanner的参与者经常在研究竞赛中与学术研究人员竞争，获得ICON算法选择挑战赛（2014年）第二名。

## 1.31. Pyomo

Pyomo是用于制定优化模型的Python软件包的集合。Pyomo由Sandia国家实验室的William
Hart、Jean-Paul Watson和加州大学戴维斯分校的David Woodruff共同开发。
Pyomo的重要扩展由Sandia国家实验室的Bethany Nicholson和John
Siirola、普渡大学的Carl Laird和Gabriel Hackebeil开发。
Pyomo是一个开放源代码项目，可免费获得，并且已获得BSD许可。
Pyomo是COIN-OR项目的一部分，
Pyomo是一种流行的开源软件包，许多政府机构和学术机构都在使用。

Pyomo允许用户以类似数学优化中常用符号的方式在Python中制定优化问题。
Pyomo支持制定优化模型的面向对象样式，该模型由各种建模组件定义：集合、标量和多维参数、决策变量、目标、约束、方程式、析取等。可以使用python数据初始化优化模型，并且可以使用电子表格、数据库和各种格式的文本文件定义外部数据源。
Pyomo支持既没有数据定义的抽象模型，又有数据定义的具体模型。在这两种情况下，Pyomo都可以分离模型和数据。

Pyomo支持数十种开源和商业求解器，包括由AMPL、PICO、CBC、CPLEX、IPOPT、Gurobi和GLPK支持的许多求解器。
Pyomo可以直接调用求解器，也可以与求解器管理器异步调用。求解器管理器支持求解器的远程异步执行，该求解器支持Pyomo脚本的并行执行。求解器交互是通过各种求解器界面执行的，具体取决于所使用的求解器。

## 1.32. Qoca

Qoca是一个GPL库，用于逐步求解具有各种目标函数的线性方程组。它包含Cassowary的可靠实现，Cassowary是用于处理曼哈顿目标函数的流行线性规划算法。它用于多个免费软件项目中，并由Monash
University维护。它具有C ++和Java版本，并提供Python和Perl的语言绑定。

## 1.33. SAS

SAS是由SAS
Institute开发的一种统计软件套件，用于数据管理、高级分析、多元分析、商业智能、刑事调查和预测性分析。SAS是一个软件套件，可以挖掘、更改、管理和检索来自各种来源的数据，并对其进行统计分析。SAS为非技术用户提供了图形化的点击式用户界面，并通过SAS语言提供了更高级的选项。

SAS程序具有用于检索和处理数据的DATA步骤，以及用于分析数据的PROC步骤。DATA步骤具有使软件采取行动的可执行语句，以及提供读取数据集或更改数据外观的指令的声明性语句。DATA步骤分为两个阶段：编译和执行。在编译阶段，处理声明性语句并识别语法错误。之后，执行阶段按顺序处理每个可执行语句。PROC步骤由调用命名过程的PROC语句组成。程序对数据集执行分析和报告，以生成统计信息、分析和图形。有300多个命名程序，每个程序都包含大量的规划和统计工作。PROC语句还可以显示结果，对数据进行排序或执行其他操作。

SAS的最大系列产品是其客户智能产品线。用于网络、社交媒体和市场分析的众多SAS模块可用于描述客户和潜在客户，预测其行为并管理和优化交流。SAS还提供了SAS欺诈框架。该框架的主要功能是监视不同应用程序、网络和合作伙伴之间的交易，并使用分析来识别表明欺诈的异常情况。SAS
Enterprise
GRC提供风险建模、场景分析和其他功能，以管理和可视化风险、合规性和公司政策。还有一个主要针对银行和金融服务组织而设计的SAS企业风险管理产品套件。SAS用于监视和管理IT系统操作的产品统称为SAS
IT管理解决方案。SAS从各种IT资产收集有关性能和利用率的数据，然后创建报告和分析。SAS的绩效管理产品在员工、部门和组织级别进行合并，并为关键绩效指标（KPI）提供图形显示。SAS供应链智能产品套件可满足供应链需求，例如预测产品需求、管理分销和库存以及优化定价。还有一套“
SAS for Sustainability
Management”软件，可以预测环境、社会和经济影响并确定运营之间的因果关系以及对环境或生态系统的影响。SAS具有针对特定行业的产品集，例如政府、零售、电信和航空航天，以及用于营销优化或高性能计算的产品集。

## 1.34. SCIP

SCIP是一个混合整数规划求解器，并且是Branch and cut和Branch and
price的框架，主要由柏林祖斯研究所开发。与大多数商业求解器不同，SCIP为用户提供了对求解过程的低级控制和信息。作为独立的求解器运行，它是混合整数程序最快的非商业求解器之一。

SCIP被实现为C可调用库。对于用户插件，提供了C ++ wrapper类。
LP松弛的求解器不是SCIP的本机组件，而是提供了开放的LP接口。当前支持的LP解算器是CLP、CPLEX、Gurobi、MOSEK、QSopt、SoPlex和Xpress。
SCIP可以在Linux、Mac、Sun和Windows操作系统上运行。

SCIP的设计基于约束的概念。它支持约20种约束类型，用于混合整数线性规划、混合整数非线性规划、混合整数全二次规划和伪布尔优化。它还可以解决Steiner树和多目标优化问题。SCIP有几个本机接口库，可以通过GAMS建模系统访问SCIP。在标准发行版中提供了与MATLAB和AMPL的接口。当前，还有两个用于Python和Java的外部接口。

## 1.35. SciPy

SciPy是一个免费的开源Python库，用于科学计算和技术计算。SciPy包含用于优化、线性代数、积分、插值、FFT、信号和图像处理、ODE求解器以及科学和工程中常见任务的模块。

SciPy建立在NumPy数组对象的基础上，并且是NumPy堆栈的一部分，该堆栈包括Matplotlib、pandas和SymPy等工具以及一组扩展的科学计算库。此NumPy堆栈具有与其他应用程序（例如MATLAB、GNU
Octave和Scilab）相似的用户。
NumPy堆栈有时也称为SciPy堆栈。SciPy库当前是根据BSD许可证发行的，其开发由开发人员社区赞助和支持，也得到NumFOCUS的支持。SciPy关键算法和功能包是Python科学计算功能的核心。

## 1.36. [SYMPHONY](https://en.wikipedia.org/wiki/COIN-OR#SYMPHONY)

网络上的单进程或多进程优化（SYMPHONY）是用于解决异构网络上的混合整数程序（MIP）的开源分支和剪切框架。它可以使用CLP、CPLEX、XPRESS或其他线性规划求解器来求解基础的线性规划。

SYMPHONY是一个可调用的库以解决MILP。库的用户可以通过提供专用于读取定制数据文件的特定于应用程序的子例程，生成特定于应用程序的切割平面或应用定制分支规则以多种方式来定制算法，从而生成定制化的分支与切割算法。该算法的大多数组件，例如搜索树管理、线性规划解决方案的管理、cut
pool管理和通信管理，都在库内部，用户无需接触。可执行文件可以采用从完全顺序到完全并行的任何数量的配置来构建，并具有独立运行的切割生成器、cut
pool和LP解算器。分布式版本当前在PVM消息传递协议支持的任何环境中运行，也可以使用任何符合OpenMP的编译器为共享内存体系结构编译相同的源代码。

SYMPHONY读取MPS（通过COIN-OR MPS阅读器）和GNU
MathProg文件。SYMPHONY没有自己的LP解算器，但可以通过Osi接口与Clp、Cplex、Xpress等求解器一起使用。切割是使用COIN的切割生成库CGL生成的。SYMPHONY还针对旅行商问题、车辆路线问题、集合划分问题、混合邮递员问题等提供了特定于结构的实现。SYMPHONY还具有一个交互式shell，用户可以在其中输入命令来执行和控制程序。

# 2. 求解器比较

给定一个数学函数，描述如何将一组输入转换为输出。优化是指从一组可用方案中，生成和选择最佳解决方案。求解器系统地选择输入值，计算目标值，并记录在此过程中找到的最佳值。

在这个通用框架中可以模拟许多现实和理论问题。例如，输入是电动机的设计参数，输出是功耗；输入是业务选择，输出是获得的利润。通常，一个优化问题可以用下面的方式表示：

给定函数

求解：A中的元素x0，使得f（x0）≤f（x）（最小化问题）

通常，A是欧几里得空间的某些子集。最大化问题可以通过将函数乘以“-1”，转化为最小化问题。

使用求解器需要以合适的编程语言定义函数，求解器将在A中传递输入值，实现的软件模块将传递计算值f（x）。下表对主要的求解器进行了比较，这些求解器具有广泛的优化范围，包括专用库或通用库：

| **求解器**                                                                         | **兼容的 编程语言**                                                   | **提供免费学术版** | **许可**                               | **备注**                                                                                                                                                                                                                                    |
|------------------------------------------------------------------------------------|-----------------------------------------------------------------------|--------------------|----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [ALGLIB](https://en.wikipedia.org/wiki/ALGLIB)                                     | C++, C\#, FreePascal, VBA                                             | Yes                | Dual (Commercial, GPL)                 | 通用库，包括优化包。                                                                                                                                                                                                                        |
| [AMPL](https://en.wikipedia.org/wiki/AMPL)                                         | C, C++, C\#, Python, Java, Matlab, R                                  | Yes                | Dual (Commercial, academic)            | 一种流行的代数建模语言，用于线性、混合整数和非线性优化。学生和AMPL课程版本是免费提供的。                                                                                                                                                    |
| [APMonitor](https://en.wikipedia.org/wiki/APMonitor)                               | Fortran, C++, Python, Matlab, Julia                                   | Yes                | Dual (Commercial, academic)            | 用于混合整数和非线性优化的微分和代数建模语言。 具有Matlab、Python和Julia的免费接口。                                                                                                                                                        |
| [Artelys Knitro](https://en.wikipedia.org/wiki/Artelys_Knitro)                     | C, C++, C\#, Python, Java, Julia, Matlab, R                           | No                 | Commercial, Academic, Trial            | 通用库，专门用于非线性优化。处理混合整数问题（MINLP）和带有平衡约束的数学程序（MPEC）。非线性最小二乘问题的专用算法。                                                                                                                       |
| [FICO Xpress](https://en.wikipedia.org/wiki/FICO_Xpress)                           | Mosel, BCL, C, C++, Java, R Python, Matlab, .Net, VB6                 | Yes                | Commercial, academic, community, trial | 优化技术和解决方案套件。包括：求解器(LP、MIP、 MIQP、MIQCQP、MISOCP、MINLP QP、QCQP、SOCP、NLP)，代数建模和过程programming语言，集成开发环境，支持用于一系列执行服务，支持将优化模型和服务打包为软件解决方案。                              |
| [GEKKO](https://en.wikipedia.org/wiki/Gekko_(optimization_software))               | Python                                                                | Yes                | Dual (Commercial, academic)            | GEKKO是一个Python软件包，用于机器学习以及混合整数和微分代数方程的优化。它与大规模求解器结合使用，可以进行线性、二次、非线性和混合整数规划（LP、QP、NLP、MILP、MINLP）。操作模式包括参数回归、数据协调、实时优化、动态仿真和非线性预测控制。 |
| **GNU Linear Programming Kit**                                                     | C                                                                     | Yes                | GPL                                    | 免费的线性规划（LP）和混合整数规划（MIP）库。                                                                                                                                                                                               |
| [GNU Scientific Library](https://en.wikipedia.org/wiki/GNU_Scientific_Library)     | C                                                                     | Yes                | GPL                                    | GNU项目提供的免费库。                                                                                                                                                                                                                       |
| [Gurobi](https://en.wikipedia.org/wiki/Gurobi)                                     | C, C++, C\#, Java, .Net, Matlab, Python, R                            | Yes                | Commercial, academic, trial            | 优化库。处理混合整数线性问题、凸二次约束和目标函数、多目标函数优化和SOS约束。                                                                                                                                                               |
| [IMSL Numerical Libraries](https://en.wikipedia.org/wiki/IMSL_Numerical_Libraries) | C, Java, C\#, Fortran, Python                                         | No                 | Proprietary                            |                                                                                                                                                                                                                                             |
| [LIONsolver](https://en.wikipedia.org/wiki/LIONsolver)                             | C++, Java                                                             | Yes                | Proprietary                            | 根据RSO原则，支持交互式和学习优化。                                                                                                                                                                                                         |
| [Math Kernel Library](https://en.wikipedia.org/wiki/Math_Kernel_Library)           | C++, Fortran                                                          | No                 | Proprietary                            | 英特尔数字库。 MKL专门研究线性代数，但包含一些与优化相关的功能。                                                                                                                                                                            |
| [MIDACO](https://en.wikipedia.org/wiki/MIDACO)                                     | C++, C\#, Python, Matlab, Octave, Fortran, R, Java, Excel, VBA, Julia | Yes                | Dual (Commercial, academic)            | 用于单目标和多目标优化的轻量级软件工具，支持MINLP和并行化。                                                                                                                                                                                 |
| [NAG Numerical Libraries](https://en.wikipedia.org/wiki/NAG_Numerical_Libraries)   | C, Fortran                                                            | No                 | Proprietary                            |                                                                                                                                                                                                                                             |
| [NMath](https://en.wikipedia.org/wiki/NMath)                                       | C\#                                                                   | No                 | Proprietary                            | 基于MKL的C＃数值库。                                                                                                                                                                                                                        |
| [Octeract Engine](https://en.wikipedia.org/wiki/Octeract_Engine)                   | C++/Python                                                            | No                 | Commercial                             | 针对一般MINLP问题的超级计算确定性全局优化求解器。 Octeract Engine使用MPI进行分布式计算。                                                                                                                                                    |
| [OptaPlanner](https://en.wikipedia.org/wiki/OptaPlanner)                           | Java                                                                  | Yes                | ASL (open source)                      | Java中的轻量级优化求解器，带有用于JPA-Hibernate、Quarkus、Spring、Jackson、JAXB等的可选集成模块。在Kotlin和Scala上也适用。                                                                                                                  |
| [SciPy](https://en.wikipedia.org/wiki/SciPy)                                       | Python                                                                | Yes                | BSD                                    | Python的通用数值和科学计算库。                                                                                                                                                                                                              |

# 参考文献

https://en.wikipedia.org/wiki/Linear_programming

https://en.wikipedia.org/wiki/List_of_optimization_software

https://en.wikipedia.org/wiki/Comparison_of_optimization_software
