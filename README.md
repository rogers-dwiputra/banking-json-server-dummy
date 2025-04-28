# Banking Interface JSON Server

Mock REST API for a dummy banking interface based

## Setup Instructions

### Prerequisites
- Node.js and npm installed on your machine

### Installation
1. Install json-server globally:
```bash
npm install -g json-server
```

2. Clone this repository or create a new project with the provided files

3. Install project dependencies:
```bash
npm init -y
npm install json-server
```

### Running the Server
1. Start the json-server:
```bash
json-server --watch db.json --port 3000
```

2. The server will be running at `http://localhost:3000` with the following endpoints:
   - User data: `http://localhost:3000/user`
   - Transactions: `http://localhost:3000/transactions`
   - Contacts: `http://localhost:3000/contacts`

## API Endpoints

### User Data
- `GET /user` - Get user account information

### Transactions
- `GET /transactions` - Get all transactions
- `GET /transactions?_sort=date&_order=desc` - Get transactions sorted by date (newest first)
- `GET /transactions?_limit=10` - Get only the 10 most recent transactions
- `GET /transactions?type=Transfer` - Filter transactions by type
- `GET /transactions?amount_gte=0` - Get only incoming transactions (positive amounts)
- `GET /transactions?amount_lt=0` - Get only outgoing transactions (negative amounts)
- `GET /transactions?q=Coffee` - Search transactions by description

### Contacts
- `GET /contacts` - Get all contacts
- `GET /contacts/:id` - Get specific contact by ID
- `POST /contacts` - Add a new contact
- `PUT /contacts/:id` - Update a contact
- `DELETE /contacts/:id` - Delete a contact

## Data Structure

The database has the following structure:

### User
```json
{
  "name": "Chelsea Immanuela",
  "accountNumber": "100899",
  "balance": 10000000.00,
  "currency": "Rp"
}
```

### Transactions
```json
{
  "id": 1,
  "date": "2022-06-30T20:10:00",
  "type": "Transfer",
  "from": "Chelsea Immanuela",
  "to": "Sendy",
  "description": "Fore Coffee",
  "amount": -75000.00
}
```

### Contacts
```json
{
  "id": 1,
  "name": "Sendy",
  "accountNumber": "200456"
}
```