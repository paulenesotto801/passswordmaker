# passswordmaker
function generateRandomPassword(length) {
    /**
     * This function generates a random password of the specified length.
     * The password will consist of a combination of uppercase letters, lowercase letters, numbers, and special characters.
     * 
     * @param {number} length - The length of the password to generate
     * @returns {string} - The randomly generated password
     */
    
    // Define the characters to be used in the password
    const uppercaseLetters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
    const lowercaseLetters = 'abcdefghijklmnopqrstuvwxyz';
    const numbers = '0123456789';
    const specialCharacters = '!@#$%^&*()_+-=[]{}|;:,.<>?';
    
    let password = '';
    
    // Generate random characters from each character set and add them to the password
    for (let i = 0; i < length; i++) {
        const randomSet = Math.floor(Math.random() * 4);
        
        switch (randomSet) {
            case 0:
                password += uppercaseLetters[Math.floor(Math.random() * uppercaseLetters.length)];
                break;
            case 1:
                password += lowercaseLetters[Math.floor(Math.random() * lowercaseLetters.length)];
                break;
            case 2:
                password += numbers[Math.floor(Math.random() * numbers.length)];
                break;
            case 3:
                password += specialCharacters[Math.floor(Math.random() * specialCharacters.length)];
                break;
        }
    }
    
    return password;
}

// Example usage
const randomPassword = generateRandomPassword(10);
console.log(randomPassword);
