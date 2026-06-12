# Patel-HW4-RTS26Summer
Homework 4: Scheduling Math  
[Link Homework 4 Parts A-C (PDF)](./Hw%204.pdf)

---

## Part C Continued:

### Two design changes [REQ: U<1.0]

#### Change 1: Increase the Period of t4 by 3 times
If you change the T4 period from 50ms to 150ms, you slow down how often t4 runs, therefore reducing CPU demand.

* Ut1 = 1/5
* Ut2 = 2/10
* Ut3 = 4/20
* Ut4 = 25/150
* Ut = 0.767

0.76 < 1.0 so increasing the period will restore feasibiity.

---

#### Change 2: Reduce the Exec Time fo the Code
If you optimize the code to reduce the exectution time, for example for t4, then the utilization should be less.

C4 reduced to 20ms ->
* Ut1 = 1/5
* Ut2 = 2/10
* Ut3 = 4/20
* Ut4 = 20/50
* Ut = 1.0

1.0=1.0   In this case the Utilization is at 100% so 20ms would be the maximum exec time needed to be feasible.

---

## Part D Industry Anchor : AUTOSAR

Since I researched AUTOSAR in homewrok 3, I thought it would be fitting to research it again. The AUTOSAR engineering team uses special configuration and timing analysis tools like Vector DaVinci Configurator or TA Tool Suite to simulate and verify task scheduling. All scheduling, task priorities, and runnable execution times are stored in a System Configuration Description file. These documents serve as critical evidence for functional safety audits to prove the system handles timing bottlenecks predictably.

Priorities are reviewed at the Runtime Environment, ensuring that safety critical runnables are mapped to high priority, preemptive OS tasks that can easily interrupt lower priority software.

If RTA or simulation shows a task misses a deadline, the design fails validation. As supported by the Vector paper, the team logs a critical defect and halts code integration. To restore feasibility without hardware changes, engineers refactor the source code to lower execution time, or adjust the periods to balance the CPU load.

---

### Sources: 
* https://cdn.vector.com/cms/content/know-how/_technical-articles/AUTOSAR/AUTOSAR_Task_Scheduling_VU_201507_PressArticle_EN.pdf
