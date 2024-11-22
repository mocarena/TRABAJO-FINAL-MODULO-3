# SimpleDEX: Exchange Descentralizado en Ethereum

## Resumen

Este proyecto consiste en un exchange descentralizado (DEX) simple, desarrollado en Solidity. Incluye dos tokens ERC-20 (`TokenA` y `TokenB`) y un contrato inteligente `SimpleDEX` que permite la provisión de liquidez, intercambios de tokens y la remoción de liquidez.

El DEX permite:
- **Agregar liquidez**: Depósito de ambos tokens en el pool.
- **Intercambiar tokens**: Realizar swaps entre `TokenA` y `TokenB` utilizando la fórmula de producto constante.
- **Remover liquidez**: Recuperar tokens depositados del pool.
- **Consultar precios**: Ver los precios de los tokens según las reservas del pool.

---

## Contratos Inteligentes

### 1. TokenA y TokenB
Estos tokens son implementaciones del estándar ERC-20, utilizando la librería de OpenZeppelin.

#### TokenA
- **Nombre**: TokenA
- **Símbolo**: TKA
- **Suministro Inicial**: 1000 TKA, asignados al deployer.

#### TokenB
- **Nombre**: TokenB
- **Símbolo**: TKB
- **Suministro Inicial**: 1000 TKB, asignados al deployer.

```solidity
contract TokenA is ERC20 {
    constructor() ERC20("TokenA", "TKA") {
        _mint(msg.sender, 1000 * 10 ** decimals());
    }
}

contract TokenB is ERC20 {
    constructor() ERC20("TokenB", "TKB") {
        _mint(msg.sender, 1000 * 10 ** decimals());
    }
}
