function dailyLog183() {
  const transactions = [
    { type: "income", amount: 120 },
    { type: "expense", amount: 35 },
    { type: "expense", amount: 20 },
    { type: "income", amount: 80 },
    { type: "expense", amount: 25 }
  ];

  const income = transactions
    .filter(item => item.type === "income")
    .reduce((sum, item) => sum + item.amount, 0);

  const expenses = transactions
    .filter(item => item.type === "expense")
    .reduce((sum, item) => sum + item.amount, 0);

  const balance = income - expenses;

  const report = {
    date: new Date().toISOString().split("T")[0],
    totalIncome: income,
    totalExpenses: expenses,
    remainingBalance: balance,
    status: balance >= 0 ? "Positive balance" : "Negative balance"
  };

  console.log("Daily Budget Report:", report);
}

dailyLog183();
