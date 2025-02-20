# Symfony API and CLI Integration with Shift4 and ACI Services

This Symfony project demonstrates integrating with Shift4 and ACI payment services through API endpoints and CLI commands.

*some API functionalities may not be available due to lack of 3DS API endpoint validation.
## Requirements

To set up and work with this application, ensure you have the following applications installed on your development machine:

- [PHP 8](https://www.php.net/)
- [Composer](https://getcomposer.org/)
- [Symfony 6.4](https://symfony.com/)

## Setup

Follow these steps to set up your local development environment:

### Install Dependencies

Install PHP dependencies using Composer:

    composer install

## Environment Variables
    cp .env.dist .env

## Run Symfony Application
### Start the Symfony application locally:
    symfony serve

## CLI Command
### Command:
    bin/console app:example {aci|shift4}

Example Command:

    php bin/console app:example shift4 --amount=100 --currency=USD --cardNumber=1234567890123456 --cardExpYear=2025 --cardExpMonth=01 --cardCvv=123
Use without prefixes: --amount  --currency --cardNumber --cardExpYear --cardExpMonth --cardCvv  // there are just for demonstration

## Setup testing environment

### Create test environment and configuration

    cp phpunit.xml.dist phpunit.xml

## Running Tests
Run PHPUnit tests to ensure everything is working correctly:

    vendor/bin/phpunit

### Service Tests:
- Shift4ServiceTest.php: Tests for Shift4Service.
- ACIServiceTest.php: Tests for ACIService.
- Mocking: Use PHPUnit's MockHttpClient to mock HTTP responses from Shift4 and ACI APIs.
- Assertions: Verify service methods (processPayment) return expected results based on mocked API responses.
