const Blockchain = require('../src/blockchain');

function mine(blockChain) {
    console.log('>>> Mining............');

    const latestBlock = blockChain.getLatestBlock();
    const prevBlockHash = latestBlock.hash;
    const currentBlockData = {
        transactions: blockChain.pendingTransactions,
        index: latestBlock.index + 1
    }
    const nonce = blockChain.proofOfWork(prevBlockHash, currentBlockData);
    const blockHash = blockChain.hashBlock(prevBlockHash, currentBlockData, nonce);

    // reward for mining
    blockChain.makeNewTransaction(1, '00000', 'miningNode');

    console.log('>>> Create new Block:\n', blockChain.creatNewBlock(nonce, prevBlockHash, blockHash));
}

const bitcoin = new Blockchain();
console.log('>>> Create new Blockchain:\n', bitcoin);

bitcoin.makeNewTransaction(120, 'JACK', 'JASON');

mine(bitcoin);

bitcoin.makeNewTransaction(1120, 'JACK', 'JASON');
bitcoin.makeNewTransaction(300, 'JASON', 'JACK');
bitcoin.makeNewTransaction(2700, 'JACK', 'JASON');

mine(bitcoin);

console.log('>>> Current Blockchain Data:\n', bitcoin);
