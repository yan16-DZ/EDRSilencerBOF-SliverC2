# EDRSilencerBOF-SliverC2
Project Overview – EDRSilencerBOF for Sliver C2
This project is an adaptation of the original EDRSilencerBOF developed by @0x3rhy for Cobalt Strike. The goal of this adaptation is to make the same capability available for use within Sliver C2, enabling red teamers and adversary emulation professionals to leverage EDRSilencer without relying solely on Cobalt Strike.

What is EDRSilencer?
EDRSilencer is an offensive security tool designed to neutralize the outbound telemetry capabilities of EDR (Endpoint Detection and Response) and antivirus software.
Rather than terminating or uninstalling these security products—which could raise alarms—EDRSilencer leverages the Windows Filtering Platform (WFP) to silently block outbound network connections made by these security processes.

By injecting low-level network filtering rules directly into the Windows networking stack, EDRSilencer effectively prevents EDR/AV processes from communicating with their remote servers. This significantly reduces the chance of detection during post-exploitation or C2 activities.

Purpose of the Sliver Adaptation
The port to Sliver C2 aims to:

Provide compatibility with an open-source C2 framework, more accessible than commercial tools.

Enable seamless use of BOF (Beacon Object File) code in Sliver through custom BOF loaders.

Integrate EDR evasion techniques directly into Sliver workflows.

Preserve stealth by avoiding process termination or modification of installed AV/EDR software.

Key Features of the Sliver Version
Automatically identifies running EDR/AV processes.

Applies Windows Filtering Platform (WFP) filters to block their outbound traffic.

Optionally cleans up filters after execution.

BOF code refactored to work within Sliver-compatible memory and execution models.

Supports custom process targeting via allow/deny lists.

