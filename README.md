# Poker44-gen17-tuner-pre6

Minimal release repository for Poker44 miner runtime scoring.

This repository is a standalone miner variant prepared for gen17 pre6 rollout with an overlay tuner fitted on labeled public benchmark chunks.

## Quick start

```bash
git clone https://github.com/tomkaba/poker44-miner-gen17-tuner-pre6.git
cd poker44-miner-gen17-tuner-pre6
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
pip install -e .
```

## Run Miner

```bash
python neurons/miner.py
```

or legacy wrapper:

```bash
./start_miner.sh HOTKEY_ID[,HOTKEY_ID2,...]
```

## Implementation

- Launcher: start_miner.sh
- Scorer entrypoint: poker44/miner_heuristics.py
- Overlay artifact scorer: models/score_chunk.py
- Entry point: neurons/miner.py
- Tuner config: models/tuner.json
- Local base runtime: models/base_runtime/
- Base pre6 scorer: models/base_runtime/score_chunk.py
- Base hand model: models/base_runtime/hand_model.npz
- Base chunk aggregator model: models/base_runtime/chunk_aggregator_model.npz
- Base feature extractor: models/base_runtime/feature_extractor_frozen.py

Manifest implementation SHA256 is computed from:

- start_miner.sh
- models/score_chunk.py
- models/tuner.json
- models/base_runtime/score_chunk.py
- models/base_runtime/hand_model.npz
- models/base_runtime/chunk_aggregator_model.npz
- models/base_runtime/feature_extractor_frozen.py
- neurons/miner.py
- poker44/__init__.py
- poker44/base/miner.py
- poker44/base/neuron.py
- poker44/miner_heuristics.py
- poker44/utils/config.py
- poker44/utils/misc.py
- poker44/utils/model_manifest.py
- poker44/validator/synapse.py
