# Electrical-load-Power-analysis-system
JAVASCRIPT
// ============================================
// ELECTRICAL LOAD & POWER ANALYSIS SYSTEM
// Department: Electrical Engineering
// Language: JavaScript
// Author: Braj Kishor Das
// ============================================

// Welcome Message
alert("⚡ Welcome to Electrical Load & Power Analysis System");

// User Details
let engineerName = prompt("Enter Engineer / Student Name:");
let department = "Electrical Engineering";

// Select Supply Type
let supplyType = prompt(
    "Select Supply Type:\n1. Single Phase\n2. Three Phase\n\nEnter 1 or 2:"
);

// Input Values
let voltage = parseFloat(prompt("Enter Voltage (V):"));
let current = parseFloat(prompt("Enter Current (A):"));
let powerFactor = parseFloat(prompt("Enter Power Factor (cosφ):"));
let hours = parseFloat(prompt("Enter Usage Time (in hours):"));
let rate = parseFloat(prompt("Enter Electricity Rate per Unit (₹):"));

let power = 0;

// Power Calculation
if (supplyType === "1") {
    power = voltage * current * powerFactor;
} else if (supplyType === "2") {
    power = Math.sqrt(3) * voltage * current * powerFactor;
} else {
    alert("Invalid Supply Type!");
}

// Convert Power to kW
let powerKW = power / 1000;

// Energy Calculation
let energy = powerKW * hours;

// Electricity Bill
let billAmount = energy * rate;

// Load Condition
let loadStatus = "";
if (powerKW < 1) {
    loadStatus = "Light Load";
} else if (powerKW >= 1 && powerKW <= 5) {
    loadStatus = "Medium Load";
} else {
    loadStatus = "Heavy Load";
}

// Efficiency Estimation (Simple Logic)
let efficiency = powerFactor * 100;

// Result Output
alert(
    "===== ELECTRICAL ANALYSIS REPORT =====\n\n" +
    "Name: " + engineerName + "\n" +
    "Department: " + department + "\n" +
    "Supply Type: " + (supplyType === "1" ? "Single Phase" : "Three Phase") + "\n\n" +
    "Voltage: " + voltage + " V\n" +
    "Current: " + current + " A\n" +
    "Power Factor: " + powerFactor + "\n\n" +
    "Power: " + powerKW.toFixed(2) + " kW\n" +
    "Energy Consumed: " + energy.toFixed(2) + " kWh\n" +
    "Load Status: " + loadStatus + "\n" +
    "Efficiency: " + efficiency.toFixed(2) + " %\n\n" +
    "Electricity Bill: ₹ " + billAmount.toFixed(2)
);

console.log("Electrical Calculation Completed Successfully");

#OUTPUTS
https://i.supaimg.com/3d2170ac-3122-4f7d-bc02-c24ef0e75ae3.jpg
https://i.supaimg.com/97234b1c-7b4d-48ae-96af-2a39aec3ae16.jpg
#OUTPUTS
