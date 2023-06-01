# PepeAI Health Monitor

Source code for the PepeAI health monitor: https://github.com/memeticofficial/health.pepeai.ml

```
Swarm state: healthy

...2vYiga, 256.0 RPS  |                                 ########                             |
...vMfXzi, 3688.5 RPS |#########################                                             |
...i9CA9T, 2776.2 RPS |                              ###############                         |
...33Pgb9, 2108.6 RPS |###############                                                       |
...Ap3RUq, 256.0 RPS  |                                     ########                         |
...7mhsNH, 256.0 RPS  |                         ########                                     |
...iRUz6M, 2767.3 RPS |               ###############                                        |
...zbDrjo, 3500.3 RPS |                                             #########################|


Legend:

# - online
J - joining     (loading blocks)
? - unreachable (port forwarding/NAT/firewall issues, see below)
_ - offline     (just disconnected)
```

See more info about PepeAI in its [testnet GitHub repo](https://github.com/memeticofficial/pepeai-testnet).

## Installation

You can run this app on your server using these commands:

```bash
git clone https://github.com/memeticofficial/health.pepeai.ml.git
cd health.pepeai.ml
pip install -r requirements.txt
flask run --host=0.0.0.0 --port=5000
```

In production, we recommend using gunicorn instead of the Flask dev server:

```bash
gunicorn app:app --bind 0.0.0.0:5000 --workers 4 --threads 10
```

## Monitoring private swarm

To monitor your private swarm instead of the public one, please replace `PUBLIC_INITIAL_PEERS` with a list of multiaddresses of your swarm's **initial peers** in [app.py](app.py). Example:

```python
INITIAL_PEERS = ['/ip4/10.1.2.3/tcp/31234/p2p/QmcXhze98AcgGQDDYna23s4Jho96n8wkwLJv78vxtFNq44']
```
