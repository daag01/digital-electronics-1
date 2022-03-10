# Lab 5: Latches and Flip-flops

<!--
![Logo](../../logolink_eng.jpg)
<p align="center">
  The Study of Modern and Developing Engineering BUT<br>
  CZ.02.2.69/0.0/0.0/18_056/0013325
</p>
-->

### Learning objectives

After completing this lab you will be able to:

* Use latches and flip-flops
* Use VHDL synchronous processes
* Understand the asynchronous and synchronous resets

In this laboratory exercise, you will study the differences between a statically controlled latch and flip-flops that are synchronized with a clock signal. In VHDL, combinational and synchronous processes will be used and the difference between asynchronous and synchronous reset will be illustrated.

### Table of contents

* [Preparation tasks](#preparation)

<a name="preparation"></a>

## Preparation tasks (done before the lab at home)

1. Write characteristic equations and complete truth tables for D, JK, T flip-flops where `q(n)` represents main output value before the clock edge and `q(n+1)` represents output value after the clock edge.
   https://editor.codecogs.com/
   \begin{align*}
       q_{n+1}^D =&~D \\
       q_{n+1}^{JK} =& \\
       q_{n+1}^T =& \\
   \end{align*}
   -->

   **D-type FF**
   | **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 0 | 0 | `q(n+1)` has the same level as `d` |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 1 | 0 | `q(n+1)` has the same level as `d` |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 0 | 1 | `q(n+1)` has the same level as `d` |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 1 | 1 | `q(n+1)` has the same level as `d` |

   **JK-type FF**
   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 0 | 0 | 0 | Output did not change |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 0 | 1 | 1 | Output did not change |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 1 | 0 | 0 | Reset |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 1 | 1 | 0 | Reset |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 0 | 0 | 1 | Set |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 1 | 0 | 1 | Toggle |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 0 | 1 | 1 | Set |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 1 | 1 | 0 | Toggle |

   **T-type FF**
   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 0 | 0 | Output did not change |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 0 | 1 | 1 | Output did not change |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 0 | 1 | Invert(toggle) |
   | ![eq_uparrow](https://user-images.githubusercontent.com/99388268/157633413-06af8354-1297-49af-8c8d-4fc41120f777.png) | 1 | 1 | 0 | Invert(toggle) |

<a name="part1"></a>
