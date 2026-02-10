# Hypothesis: {Title}

## Bug / Issue

{ID, title, link}

## Summary

{2-3 sentences: what happens, when, and impact}

## Root Cause Analysis

### Primary Cause

{What is the root cause and where in the code}

**Files:**
- {file-path:line-number}

**Evidence:**
```
{Code snippet, retention chain, error output, etc.}
```

### Why This Causes the Problem

1. {Step-by-step chain from cause to symptom}

### Contributing Factors

| Factor | Status | Impact |
|--------|--------|--------|
| {Factor 1} | {On/Off/Unknown} | {What happens if this is wrong} |

## Proposed Fix

```
{Code or pseudocode for the fix}
```

### What This Fixes

- {Leak vector / bug path this addresses}

### What This Doesn't Fix

- {Known limitations, separate issues}

## Evidence Confidence

- **High confidence:** {Evidence directly observed}
- **Medium confidence:** {Evidence inferred}
- **Low confidence / Speculative:** {Hypothesized but not proven}

## Validation Plan

- [ ] {How to prove the fix works — heap snapshot, test, etc.}
- [ ] {Additional verification steps}
