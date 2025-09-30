# Ass1
```python
import hashlib
import time

class Block:
    def _init_(self, index, data, previous_hash='0'):
        self.index = index
        self.timestamp = time.time()
        self.data = data
        self.previous_hash = previous_hash
        self.nonce = 0
        self.hash = self.mineBlock()

    def calculateHash(self):
        content = f"{self.index}{self.timestamp}{self.data}{self.previous_hash}{self.nonce}"
        return hashlib.sha256(content.encode()).hexdigest()

    def mineBlock(self, difficulty=3):
        prefix = '0' * difficulty
        while True:
            hash_attempt = self.calculateHash()
            if hash_attempt.startswith(prefix):
                return hash_attempt
            self.nonce += 1

Define blockchain using array
blockchain = []

setBlock method
def setBlock(data):
    index = len(blockchain)
    previous_hash = blockchain[-1].hash if blockchain else '0'
    block = Block(index, data, previous_hash)
    blockchain.append(block)

getBlock method
def getBlock(index):
    if 0 <= index < len(blockchain):
        return vars(blockchain[index])
    return "Block not found"

blocksExplorer method
def blocksExplorer():
    for block in blockchain:
        print(vars(block))
Example usage
setBlock("Genesis Block")
setBlock("Second Block")
setBlock("Third Block")

blocksExplorer()
```

Let me know if you want it in another language like *JavaScript* or *C++*.
