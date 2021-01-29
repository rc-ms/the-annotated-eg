# ElectionGuard Precinct Scan Implementation

## Overview

The ElectionGuard SDK by design can be used in a variety of use cases. This page discusses the "default" use case of ElectionGuard: an end-to-end verifiable election that uses precinct scanners where ballots are inserted (and approved) by voters directly (as distinct from scanners used solely for central tabulation)

## Current Precinct Scan Voter Experience

A typical voter flow for a precinct scan system is illustrated below. 

After a voter has acquired their ballot, they fill it out by hand or using a ballot marking device. When they are finished they insert the ballot into the scanner. The scanner then scans and interprets the ballot and generates a [cast vote record](), an electronic representation of the voter's selections.

If all contests in a ballot are filled out properly and interpreted as such by the scanner, the ballot is accepted and the voter is free to leave the voting booth. 

If the scanner interprets the voter has voted for more options than the ballot contests allow (called an _overvote_), the scanner stops the ballot from being deposited into the ballot box and prompts the voter whether they would like to have the ballot returned to fix the discrepancy. If the voter agrees, a poll worker is alerted and the ballot remediated by whatever process obtains, which could involve issuance of a new ballot and "spoiling" of the overvoted ballot. 

The scanner can also determine whether the voter didn't fill out all the contests available (called an _undervote_). The scanner can be programmed to follow the same process as an overvote (returning the ballot for remediation), but election administrators often assume the undervote is intentional by the voter 

## Adapting Precinct Scan for End-to-end Verifiability (E2E-V)