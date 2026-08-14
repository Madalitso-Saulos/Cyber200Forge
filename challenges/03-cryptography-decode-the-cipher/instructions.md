# Scenario & Instructions

## Scenario

An intercepted message was passed between two training-exercise "agents." It looks like gibberish, but every layer is a well-known, reversible encoding or classical cipher. Peel it back one layer at a time.

## Task A — Layered Encoding

You are given the following string:

```text
NTM1OTRlNTQ3Yjc5NmU2YzcyNjU2NjVmNjI3MzVmNzI2MTcwNjI3MTc2NjE3NDVmNzE3MjcwNjI3MTcyNzE3ZA==
```

1. Identify the outermost encoding by its charset and padding.
2. Decode it, then identify the *next* layer by its charset.
3. Decode that layer, then identify the final cipher (hint: it shifts every letter by a fixed amount).
4. Recover the plaintext flag, in the format `FLAG{...}`.

## Task B — XOR With a Known Key

You are given the following hex-encoded, XOR-"encrypted" ciphertext, and told the repeating key is a 3-character lowercase word related to this repository's subject:

```text
253827240f1e0c063952073911471006061552160a0609
```

1. Convert the hex string back to raw bytes.
2. XOR each byte against the repeating key.
3. Recover the plaintext flag, in the format `FLAG{...}`.

## Expected Results

Two recovered plaintext flags, one for Task A and one for Task B.

## Evidence

Save your CyberChef "recipe" (the chain of operations you used) as a screenshot or exported recipe file for each task.
