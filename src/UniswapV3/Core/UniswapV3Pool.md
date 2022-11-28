# Diving into Uniswap Pools

## Introduction

The Uniswap V3 pools are one of the key parts of the protocol. Understanding what goes on behind the scenes will give us a better understanding how solidity can be used to accomplish different tasks. 

## Layout

The breakdown is layout is down by function. This will include any interface descriptions, library usage, or other critical information that allows that function to perform as intended. As well as a high-level line by line breakdown of what is happening at any given point during that function. There are 19 in total. They are listed below with their paramters and return values. 

## List of functions:

1. constructor() 
2. function checkTicks(int24 tickLower, int24 tickUpper)
3. function _blockTimestamp()
4. function balance0() private view returns (uint256) 
5. function balance1() private view returns (uint256)
6. function snapshotCumulativesInside(int24 tickLower, int24 tickUpper) external view override noDelegateCall returns (int56 tickCumulativeInside, uint160 secondsPerLiquidityInsideX128, uint32 secondsInside)
7. function observe(uint32[] calldata secondsAgos)external view override noDelegateCall returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s)
8. function increaseObservationCardinalityNext(uint16 observationCardinalityNext)
        external
        override
        lock
        noDelegateCall
9. function initialize(uint160 sqrtPriceX96) external override
10. function _modifyPosition(ModifyPositionParams memory params)
        private
        noDelegateCall
        returns (
            Position.Info storage position,
            int256 amount0,
            int256 amount1
        )
11. function _updatePosition(
        address owner,
        int24 tickLower,
        int24 tickUpper,
        int128 liquidityDelta,
        int24 tick
    ) private returns (Position.Info storage position)
12. function mint(
        address recipient,
        int24 tickLower,
        int24 tickUpper,
        uint128 amount,
        bytes calldata data
    ) external override lock returns (uint256 amount0, uint256 amount1)
13. function collect(
        address recipient,
        int24 tickLower,
        int24 tickUpper,
        uint128 amount0Requested,
        uint128 amount1Requested
    ) external override lock returns (uint128 amount0, uint128 amount1)
14. function burn(
        int24 tickLower,
        int24 tickUpper,
        uint128 amount
    ) external override lock returns (uint256 amount0, uint256 amount1)
15. function swap(
        address recipient,
        bool zeroForOne,
        int256 amountSpecified,
        uint160 sqrtPriceLimitX96,
        bytes calldata data
    ) external override noDelegateCall returns (int256 amount0, int256 amount1)
16. function flash(
        address recipient,
        uint256 amount0,
        uint256 amount1,
        bytes calldata data
    ) external override lock noDelegateCall
17. function setFeeProtocol(uint8 feeProtocol0, uint8 feeProtocol1) external override lock onlyFactoryOwner
18. function setFeeProtocol(uint8 feeProtocol0, uint8 feeProtocol1) external override lock onlyFactoryOwner 
19. function collectProtocol(
        address recipient,
        uint128 amount0Requested,
        uint128 amount1Requested
    ) external override lock onlyFactoryOwner returns (uint128 amount0, uint128 amount1)