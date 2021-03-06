---
title: SpinLockSafe rule (storport)
description: This rule verifies that the IoStartNextPacket and IoCompleteRequest routines are not called while holding a spin lock.
ms.assetid: 12D36178-C00D-44A7-9DA0-E0663DF1FFDC
ms.date: 05/21/2018
keywords: ["SpinLockSafe rule (storport)"]
topic_type:
- apiref
api_name:
- SpinLockSafe
api_type:
- NA
ms.localizationpriority: medium
---

# SpinLockSafe rule (storport)


This rule verifies that the **IoStartNextPacket** and **IoCompleteRequest** routines are not called while holding a spin lock. The rule keeps track of the number of spin locks held at any time, and if that number is not 0 when either routine is called, the driver fails the rule.

|              |          |
|--------------|----------|
| Driver model | Storport |

How to test
-----------

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">At compile time</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Run [Static Driver Verifier](https://msdn.microsoft.com/library/windows/hardware/ff552808) and specify the <strong>SpinLockSafe</strong> rule.</p>
Use the following steps to run an analysis of your code:
<ol>
<li>[Prepare your code (use role type declarations).](https://msdn.microsoft.com/library/windows/hardware/hh454281#preparing-your-source-code)</li>
<li>[Run Static Driver Verifier.](https://msdn.microsoft.com/library/windows/hardware/hh454281#running-static-driver-verifier)</li>
<li>[View and analyze the results.](https://msdn.microsoft.com/library/windows/hardware/hh454281#viewing-and-analyzing-the-results)</li>
</ol>
<p>For more information, see [Using Static Driver Verifier to Find Defects in Drivers](https://msdn.microsoft.com/library/windows/hardware/hh454281).</p></td>
</tr>
</tbody>
</table>

Applies to
----------

[**IoAcquireCancelSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff548196)
[**IoCompleteRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548343)
[**IoReleaseCancelSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff549550)
[**IoStartNextPacket**](https://msdn.microsoft.com/library/windows/hardware/ff550358)
[**KeAcquireSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff551917)
[**KeAcquireSpinLockAtDpcLevel**](https://msdn.microsoft.com/library/windows/hardware/ff551921)
[**KeReleaseSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff553145)
[**KeReleaseSpinLockFromDpcLevel**](https://msdn.microsoft.com/library/windows/hardware/ff553150)
 

 





