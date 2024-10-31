Sources: [OpenZeppelin](https://github.com/openzeppelin/openzeppelin-contracts/)
# ERC20Practice
Learn Solidity basics via ERC20 smart contracts.

## Practice 1
```Solidity
// SPDX-License-Identifier: MIT
// MyERC20 version 0.0.1

pragma solidity ^0.8.20;
import {ERC20} from "./ERC20.sol";

contract MyERC20 is ERC20 {
    uint256 public _initialSupply = 1000000 * (10**18);

    constructor(string memory name_, string memory symbol_) ERC20(name_, symbol_) {
        _mint(_msgSender(), _initialSupply);
    }

    function mint(address to, uint256 value) public {
        _mint(to, value);
    }
}

```

## Practice 2
```Solidity
// SPDX-License-Identifier: MIT
// MyERC20 version 0.0.2

pragma solidity ^0.8.20;
import {ERC20} from "./ERC20.sol";

contract MyERC20 is ERC20 {
    uint256 public _initialSupply = 1000000 * (10**18);
    address public _owner;

    constructor(string memory name_, string memory symbol_) ERC20(name_, symbol_) {
        _mint(_msgSender(), _initialSupply);
        _owner = _msgSender();
    }

    function mint(address to, uint256 value) public {
        require(_owner == _msgSender(), "caller is not owner");
        _mint(to, value);
    }
}
```

## Google Forms
[https://forms.gle/TorPmmP2zGrdyeW88/](https://forms.gle/TorPmmP2zGrdyeW88/)
