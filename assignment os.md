

<div class="container">
<h1>
Operating Systems
</h1>
<h2>
Assignment 01
</h2>
<p>
Name: MD. Arif Faysal Nayem
<p>ID: 011201194</p>
<p>Course: Operating Systems</p>
Section: C
</div>




### 1. Size of the offset

The offset size is determined by the page size.

$$\text{Page size} = 2^{12} \Rightarrow \text{Offset size} = 12 \text{ bits}$$

### 2. Number of virtual pages in virtual memory

Virtual pages = Virtual address space / Page size

$$
\frac{2^{32}}{2^{12}} = 2^{20} \text{ virtual pages}
$$

### 3. Number of bits required for VPN (Virtual Page Number)

VPN bits = Total virtual address bits - offset bits


$$32 - 12 = 20 \text{ bits}$$

### 4. Number of bits required for PFN (Page Frame Number)

 $$\text{Physical memory size} =2^{33} \text{bytes}$$

Number of physical frames = Physical memory / Page size

$$
\frac{2^{33}}{2^{12}} = 2^{21} \text{ frames}
$$

$$\text{PFN bits} = log_2 (\text{number of physical frames}) = 21 \text{bits}$$


### 5. Size of a single page table

Number of entries in page table = number of virtual pages = $$2^{20}$$

Size of each entry = 4 bytes

$$
\text{Page table size} = 2^{20} \times 4 = 4 \times 2^{20} = 4 \text{ MB}
$$


### 6. Design a multi-level page table

Since the VPN is 20 bits, and the page size offset is 12 bits, we can split the VPN into multiple parts for hierarchical paging.

Approach: 2-level page table.

- Split 20 bits VPN into two parts of 10 bits each:

  - First-level index: 10 bits → $$2^{10} = 1024$$ entries
  - Second-level index: 10 bits → $$2^{10} = 1024$$ entries

Each page table (both levels) fits in one page (4 KB):

- Each page table entry is 4 bytes
- Number of entries per page table = $$4 \text{ KB} / 4 \text{ bytes} = 1024$$

This matches the 10-bit index size. 

So, each page table can fit in a single page, making memory management efficient.

