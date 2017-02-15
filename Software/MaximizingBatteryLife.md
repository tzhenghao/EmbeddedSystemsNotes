Clock gating

State retention power gating


If we benchmark the cost of fetching and executing an instruction as 1 unit of energy, then the incremental cost of accessing a variable held in TCM is roughly 1/25, the cost of an L1 cache access around 1/6 and an L2 cache access around 1. The cost of an external RAM access is a whopping 7 times the cost of an instruction execution.


Think of this another way: for each external RAM access, we can execute 7 instructions, carry out 40 cache accesses or access TCM around 170 times for the same energy cost.

Brought to a conclusion that computation is cheap, while communication is expensive.
Moving data around costs a lot more energy than processing it.


Data Efficiency

	1. Keep it close in terms of accessing memory.
	2. Access it less. Access data either less often or by exhibiting greater locality.

Scratchpad Memory - an area of fast, wide SRM implemented on the chip and connected as directly as possible to the core. In ARM's case, it's the TCM.

TCM in ARM cores - usually separate slave ports within the AXI interconnect matrix which allow DMA access to TCM regions.

Cost of a cache access is 4-25x more than SPM access.

Performance increases (with diminishing returns) as cache size increases. Power consumption increases as well.

Turn on instruction cache!

Large data structures can be problematic.
Watch out for arrays by column - cache unfriendly when row size >  cache line length.

Strip mining - accessing a 2D matrix in strips that are only as long as cache line length so they can be used immediately.

Don’t use recursion unless either the alternatives are worse for data locality, or you are confident that the recursive call can be tail-optimized by the compiler.

Computation Efficiency

Lesser instructions leads to less energy consumption.

Use unsigned integer counters, count down and test for equality with zero as termination condition.

Fixed point implementation is more efficient than floating point.


The Thumb instruction set is designed explicitly to improve code density.

Pros of Thumb:
It has the attendant benefit of improving performance for narrow memory systems.

Cons of Thumb:
While code density certainly improves, the instruction count increases at the same time. This is due to the reduced functionality of individual Thumb instructions as compared against individual ARM instructions.

Very system and application-dependent
