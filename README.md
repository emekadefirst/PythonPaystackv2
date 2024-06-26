# Pystack

This Python package provides a set of classes to interact with the Paystack API for handling transactions, customers, subscriptions, and webhooks.

## Installation

To use this package, you need to have Python installed. You can install the package using pip:

```
pip install pypstk
```

## Usage

### 1. Payment

```python
from pypstk.payment import Payment

email = "customer@email.com"
amount = "20000"
secret_key = "your secret_key from api"

new_payment = Payment(email, amount, secret_key)
transaction_data = new_payment.initialize_transaction()
print(transaction_data)

# Sample output:
# {'references': '8pr6trcjj5', 'url': 'https://checkout.paystack.com/j62hay03a7dj6iu'}

```


### 3. Subscription

```python
from pypstk.subscription import Subscription

# Initialize subscription payment
name = "Monthly Retainer"
interval = "monthly"
amount = 500000
secret_key = "sk_test_daf386e7071c4613e54e4b71f43926409abd811e"

pay_subscription = Subscription(name, interval, amount, secret_key)
pay_subscription.initialize_payment()
pay_subscription.payment_status()
```

### 4. Payment Status

```python
from pypstk.status import Verify

# Check webhook status
reference = "YOUR_REFERENCE"
secret_key = "YOUR_SECRET_KEY"

hook = Hook(reference, secret_key)
status = hook.status()
print(status)
```

## Contributors

- [Emekadefirst](https://github.com/emekadefirst)
- I used [Olabode](https://github.com/Olabode-cmd) template to test this in an api

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
