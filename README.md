# StudyFund - Financial DApp

Full source code, Solidity contract and ABI, Flask backend, HTML/CSS/JavaScript, tests, screenshots and seven-page report are included in **StudyFund_Submission.zip**.

The archive contains a single `StudyFund/` directory. Download and extract it to inspect or run the project. The included README and DEPLOYMENT guide cover local setup and Sepolia wallet deployment.

## Render deployment

Runtime: Python. Free web service.

Build command:
```
python -m zipfile -e StudyFund_Submission.zip . && pip install -r StudyFund/requirements.txt
```

Start command:
```
gunicorn --chdir StudyFund app:app --bind 0.0.0.0:$PORT --workers 2 --threads 4 --timeout 120
```

Environment: `PYTHON_VERSION=3.11.11`, `CHAIN_ID=11155111`. Set `ENABLE_DEPLOY_UI=true` temporarily to use `/deploy` with MetaMask; after deployment set the returned `CONTRACT_ADDRESS`, `DEPLOYMENT_BLOCK`, a Sepolia `RPC_URL`, and disable the helper.

The server does not store or request wallet private keys. Until the contract is configured, the UI explicitly displays setup status and disables savings writes. It never invents balances or transactions.

## Verification

39 contract/backend tests and 14 browser checks passed on a local Ethereum chain. Sepolia and real MetaMask evidence require actual wallet deployment. No video is needed for the assignment.
