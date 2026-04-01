# Oracle-mock-owner-sets-price-others-read-
Oracle mock (owner sets price, others read)
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/access/Ownable.sol";

contract PriceOracleMock is Ownable {
    mapping(bytes32 => uint256) public prices;

    function setPrice(bytes32 pair, uint256 price) public onlyOwner {
        prices[pair] = price;
    }

    function getPrice(bytes32 pair) public view returns (uint256) {
        return prices[pair];
    }
}
