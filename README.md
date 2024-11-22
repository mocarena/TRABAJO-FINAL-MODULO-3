# SimpleDEX: Intercambio Descentralizado de Tokens ERC-20

## Descripción
Este proyecto implementa un **Exchange Descentralizado (DEX)** simple en la blockchain de Ethereum. Permite la interacción con dos tokens ERC-20 (`TokenA` y `TokenB`), brindando funcionalidades para añadir liquidez, intercambiar tokens y retirar liquidez.

## Contratos
1. **TokenA**: Representa un token ERC-20 llamado `TokenA` con símbolo `TKA`.
2. **TokenB**: Representa un token ERC-20 llamado `TokenB` con símbolo `TKB`.
3. **SimpleDEX**: El contrato principal que gestiona el intercambio, liquidez y precios.

## Funcionalidades Principales
### **SimpleDEX**
1. **Añadir liquidez (`addLiquidity`)**  
   Permite añadir reservas de `TokenA` y `TokenB` al DEX.

2. **Intercambiar tokens (`swapAforB`, `swapBforA`)**  
   Permite intercambiar `TokenA` por `TokenB` y viceversa, aplicando un fee del 0.3%.

3. **Retirar liquidez (`removeLiquidity`)**  
   Permite al propietario retirar tokens desde las reservas del DEX.

4. **Obtener precios (`getPrice`)**  
   Calcula el precio de un token en términos del otro.

5. **Cálculo de intercambio (`getAmountOut`)**  
   Calcula la cantidad de tokens que un usuario recibirá basado en las reservas actuales y el fee.

## Eventos
### **SimpleDEX**
1. **`LiquidityAdded(address indexed provider, uint256 amountA, uint256 amountB)`**  
   Emite un evento al añadir liquidez.  
   - **`provider`**: Dirección del usuario que añade liquidez.  
   - **`amountA`**: Cantidad de `TokenA` añadida.  
   - **`amountB`**: Cantidad de `TokenB` añadida.  

2. **`TokensSwapped(address indexed swapper, address indexed fromToken, address indexed toToken, uint256 inputAmount, uint256 outputAmount)`**  
   Emite un evento al realizar un intercambio de tokens.  
   - **`swapper`**: Dirección del usuario que realiza el intercambio.  
   - **`fromToken`**: Dirección del token enviado por el usuario.  
   - **`toToken`**: Dirección del token recibido por el usuario.  
   - **`inputAmount`**: Cantidad del token de entrada.  
   - **`outputAmount`**: Cantidad del token de salida.  

3. **`LiquidityRemoved(address indexed provider, uint256 amountA, uint256 amountB)`**  
   Emite un evento al retirar liquidez.  
   - **`provider`**: Dirección del propietario que retira liquidez.  
   - **`amountA`**: Cantidad de `TokenA` retirada.  
   - **`amountB`**: Cantidad de `TokenB` retirada.  

4. **`PriceQueried(address indexed tokenQueried, uint256 price)`**  
   Emite un evento al consultar el precio de un token.  
   - **`tokenQueried`**: Dirección del token cuyo precio se consulta.  
   - **`price`**: Precio calculado del token.  

5. **`AmountOutCalculated(uint256 inputAmount, uint256 outputAmount)`**  
   Emite un evento al calcular la cantidad de tokens a recibir en un intercambio.  
   - **`inputAmount`**: Cantidad de tokens proporcionados por el usuario.  
   - **`outputAmount`**: Cantidad de tokens que se recibirá tras aplicar las tarifas.  

## Despliegue
### Requisitos
- **Remix**: Entorno de desarrollo para Solidity.
- **MetaMask**: Extensión para interactuar con la blockchain.
- **Prueba con la red Scroll Sepolia**.

### Pasos
1. Copiar los contratos `TokenA.sol`, `TokenB.sol` y `SimpleDEX.sol` en Remix.
2. Desplegar primero `TokenA` y `TokenB`.
3. Usar las direcciones de `TokenA` y `TokenB` al desplegar `SimpleDEX`.
4. Interactuar con las funciones utilizando la interfaz de Remix o integraciones personalizadas.

---
