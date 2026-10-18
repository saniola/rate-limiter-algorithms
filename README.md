# Rate Limiter Algorithms

Python implementations of two common rate-limiting strategies for controlling how frequently users can send messages.

## Contents

### `task1.py` — Sliding Window Rate Limiter

Tracks each user's message timestamps in a deque and enforces a maximum number of requests within a rolling time window (`window_size` seconds). Expired timestamps are cleaned up on each check.

### `task2.py` — Throttling Rate Limiter

Enforces a fixed minimum interval between a user's consecutive messages, rejecting any message sent before `min_interval` seconds have elapsed since the last one.

Both implementations expose the same interface:

- `can_send_message(user_id)` — checks whether a message is currently allowed.
- `record_message(user_id)` — records a message if allowed and returns whether it succeeded.
- `time_until_next_allowed(user_id)` — returns the wait time before the next message is allowed.

Each script includes a simulation of a stream of incoming messages from multiple users to demonstrate the limiter's behavior.

## Stack

- Python 3 (standard library only)

## Usage

```bash
python task1.py
python task2.py
```
