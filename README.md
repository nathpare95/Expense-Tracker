# Expense-Tracker
Expense Tracker
const addTransactionForm = document.querySelector('#add-transaction-form');
const transactionList = document.querySelector('#transaction-list');
const transactionCategory = document.querySelector('#transaction-category');
const transactionAmount = document.querySelector('#transaction-amount');
const transactionDate = document.querySelector('#transaction-date');

function addTransaction(event) {
  event.preventDefault();
  const category = transactionCategory.value;
  const amount = transactionAmount.value;
  const date = transactionDate.value;

  if (category.trim() === '' || amount.trim() === '' || date.trim() === '') {
    // display error message to user
    return;
  }

  const transaction = {
    id: Date.now(),
    category,
    amount,
    date
  };

  // add transaction to database or local storage
  // update UI with new transaction
  // clear input fields
  transactionCategory.value = '';
  transactionAmount.value = '';
  transactionDate.value = '';
}

addTransactionForm.addEventListener('submit', addTransaction);
