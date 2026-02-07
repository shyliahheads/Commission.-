# Commission.-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Weekly Commission Report</title>
<style>
    body {
        font-family: Arial, Helvetica, sans-serif;
        background: linear-gradient(135deg, #4facfe, #00f2fe);
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0;
    }

    .report-box {
        background: white;
        padding: 40px;
        border-radius: 15px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        width: 500px;
        text-align: center;
    }

    h1 {
        margin-bottom: 20px;
        color: #333;
    }

    p {
        font-size: 18px;
        color: #555;
        line-height: 1.6;
    }
</style>
</head>
<body>

<div class="report-box" id="output"></div>

<script>
// Username prompt
var username = prompt("Enter your name:");

var subtotal = 0;
var sale;

// Posttest loop using do...while
do {
    sale = prompt("Enter sale amount in dollars and cents. Type Done when finished:");

    if (sale !== null && sale.toLowerCase() !== "done") {
        subtotal += parseFloat(sale);
    }

} while (sale !== null && sale.toLowerCase() !== "done");

// Commission variables
var rate = 0;
var commission = 0;
var earnings = 0;

// Range checks
if (subtotal <= 0) {
    rate = 0;
}
else if (subtotal >= 0.01 && subtotal <= 499.99) {
    rate = 0.05;
}
else if (subtotal >= 500 && subtotal <= 999.99) {
    rate = 0.10;
}
else {
    rate = 0.15;
}

// Calculations
commission = subtotal * rate;
earnings = subtotal + commission;

// Currency formatting
var subtotalFmt = subtotal.toLocaleString(undefined, {style:'currency', currency:'USD'});
var commissionFmt = commission.toLocaleString(undefined, {style:'currency', currency:'USD'});
var earningsFmt = earnings.toLocaleString(undefined, {style:'currency', currency:'USD'});
var rateFmt = (rate * 100).toFixed(2) + "%";

// Single output statement
document.getElementById("output").innerHTML =
    "<h1>Hello " + username + ", Here is your Weekly Commission Report.</h1>" +
    "<p>Your sales total is " + subtotalFmt + ", so your commission rate is " + rateFmt + "</p>" +
    "<p>Your total commission is " + commissionFmt + ".</p>" +
    "<p>Your total earnings are " + earningsFmt + "</p>";
</script>

</body>
</html>






















[Start]

   ↓
Enter Username

   ↓
Set Subtotal = 0

   ↓
Enter Sale Amount
(Type Done to finish)

   ↓
Is input "Done"?
   ├─ Yes → Go to Commission Check
   └─ No  → Add Sale to Subtotal → Back to Enter Sale

Commission Check:

   ↓
Subtotal ≤ 0 ? → Rate = 0%
0.01–499.99 ? → Rate = 5%
500–999.99 ? → Rate = 10%
1000+ ? → Rate = 15%

   ↓
Calculate Commission

   ↓
Calculate Total Earnings

   ↓
Display Report

   ↓
[End]



















