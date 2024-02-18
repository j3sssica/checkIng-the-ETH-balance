# checkIng-the-ETH-balance
This script checks the balance of a given Ethereum address
from web3 import Web3

# Connect to an Ethereum node (you can use Infura or run your own node)
w3 = Web3(Web3.HTTPProvider('https://mainnet.infura.io/v3/your_infura_api_key'))

def get_eth_balance(address):
    try:
        # Check if the address is valid
        if not w3.isAddress(address):
            print("Invalid Ethereum address")
            return

        # Get the balance in Wei
        balance_wei = w3.eth.getBalance(address)

        # Convert Wei to Ether
        balance_eth = w3.fromWei(balance_wei, 'ether')

        print(f"Balance for address {address}: {balance_eth} ETH")
    except Exception as e:
        print(f"Error: {e}")

# Replace 'your_ethereum_address' with the actual Ethereum address you want to check
address_to_check = 'your_ethereum_address'
get_eth_balance(address_to_check)

Make sure to install the web3 library before running the script:
pip install web3

Remember to replace 'your_infura_api_key' with your actual Infura API key and 'your_ethereum_address' with the Ethereum address you want to check.

This script demonstrates a basic interaction with the Ethereum blockchain by querying the balance of a given address. Depending on your requirements, you can extend this script to perform various transactions, deploy smart contracts, or interact with other blockchain features.
