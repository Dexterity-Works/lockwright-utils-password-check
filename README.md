# lockwright-utils-password-check

A utility library to check the strength of passwords and passphrases based on configurable rules.

Site: [lockwright.dexterity.works](https://lockwright.dexterity.works)

Community fork of PearPass (Apache 2.0). Not affiliated with or endorsed by Tether Data or the Pears project.

## Table of Contents

- [Features](#features)
- [Security Notice](#security-notice)
- [Installation](#installation)
- [Usage Examples](#usage-examples)
- [Dependencies](#dependencies)
- [Related Projects](#related-projects)

## Features

This utility provides functions to check the strength of passwords and passphrases based on configurable rules:

**Password Validation:**
- Minimum length requirements
- Uppercase and lowercase character inclusion
- Number inclusion
- Special character inclusion

**Passphrase Validation:**
- Minimum word count
- Unique words verification
- Capital letter inclusion
- Symbol inclusion
- Number inclusion

## Security Notice

Imports stay `@tetherto/pearpass-utils-password-check`. That npm name is not this fork if you install it from the npm registry.

## Installation

```bash
npm install git+https://github.com/Dexterity-Works/lockwright-utils-password-check.git
```

## Usage Examples

### Checking Password Strength
```javascript
import { checkPasswordStrength } from '@tetherto/pearpass-utils-password-check';

// With default rules
const result = checkPasswordStrength('Test123!');
console.log(result.strengthType); // safe

// With custom rules
const customResult = checkPasswordStrength('Test1234', {
    length: 8,
    includeSpecialChars: false,
    lowerCase: true,
    upperCase: true,
    numbers: true
});
console.log(customResult.strengthType); // safe
console.log(customResult.rules); // Detailed rules assessment
```

### Checking Passphrase Strength
```javascript
import { checkPassphraseStrength } from '@tetherto/pearpass-utils-password-check';

// With default rules
const words = ['Test1!', 'Word2@', 'Example3#', 'Unique', 'Safe', 'Pass', 'Phrase', 'Another4$'];
const result = checkPassphraseStrength(words);
console.log(result.strength); // safe

// With custom rules
const customResult = checkPassphraseStrength(words, {
    capitalLetters: true,
    symbols: true,
    numbers: true,
    words: 6
});
console.log(customResult.strengthType); // safe
console.log(customResult.rules); // Detailed rules assessment
```

## Dependencies

This package has no runtime dependencies.

## Related Projects

- [lockwright-app-mobile](https://github.com/Dexterity-Works/lockwright-app-mobile) - Lockwright for mobile
- [lockwright-app-desktop](https://github.com/Dexterity-Works/lockwright-app-desktop) - Lockwright for desktop
- [lockwright-lib-ui-react-native-components](https://github.com/Dexterity-Works/lockwright-lib-ui-react-native-components) - Lockwright UI kit
- [tether-dev-docs](https://github.com/Dexterity-Works/tether-dev-docs) - Documentations and guides for developers

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](./LICENSE) file for details.