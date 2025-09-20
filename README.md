<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Certificate Verification</title>
  <style>
    body {
      margin:0;
      font-family: "Segoe UI", Arial, sans-serif;
      background: linear-gradient(135deg, #0077b6, #00b4d8);
      display:flex;
      justify-content:center;
      align-items:center;
      height:100vh;
      color:#fff;
    }
    .box {
      background: rgba(255,255,255,0.1);
      padding:40px;
      border-radius:16px;
      width:95%;
      max-width:650px;
      box-shadow:0 8px 25px rgba(0,0,0,0.3);
      text-align:center;
    }
    h1 {margin-bottom:20px;}
    input {
      width:100%;
      padding:12px;
      border-radius:8px;
      border:none;
      margin:15px 0;
      font-size:1rem;
    }
    button {
      background:#fff;
      color:#0077b6;
      border:none;
      padding:12px 24px;
      font-size:1rem;
      border-radius:8px;
      cursor:pointer;
      transition:background .3s;
    }
    button:hover {background:#caf0f8;}
    #result {
      margin-top:25px;
      text-align:left;
      background:rgba(0,0,0,0.2);
      padding:20px;
      border-radius:12px;
    }
    .verified {color:#90ee90;}
    .notfound {color:#ffb3b3;}
    .field {margin:6px 0;}
    strong {color:#fff;}
  </style>
</head>
<body>
  <div class="box">
    <h1>Certificate Verification</h1>
    <p>Enter your Certificate Number:</p>
    <input type="text" id="certId" placeholder="Enter Certificate No">
    <button onclick="verify()">Verify</button>
    <div id="result"></div>
  </div>

<script>
const certData = [
  {id:"EEPL/VOC/25/07/119", name:"PRANAV KACHHAP", project:"LIBRARY MANAGEMENT SYSTEM", college:"GOVERNMENT POLYTECHNIC RANCHI", branch:"CSE"},
  {id:"EEPL/VOC/25/07/113", name:"ANURAG XESS", project:"HYDRAULIC SYSTEM FOR VARIOUS EQUIPMENT DESIGN", college:"GOVERNMENT POLYTECHNIC RANCHI", branch:"MECHANICAL"},
  {id:"EEPL/VOC/25/07/114", name:"GORACHAND TUDU", project:"DESIGN OF HYDRAULIC SYSTEM", college:"GOVERNMENT POLYTECHNIC RANCHI", branch:"MECHANICAL"},
 {id:"EEPL/VOC/25/07/116", name:"NIKHIL KUMAR KISHKU ", project:"ONLINE TEACHING MANAGEMENT", college:"GOVERNMENT POLYTECHNIC RANCHI", branch:"COMPUTER SCIENCE AND ENGINEERING (CSE)"},
 {id:"EEPL/VOC/25/07/114", name:"NIKHIL KUMAR KISHKU ", project:"ONLINE TEACHING MANAGEMENT", college:"GOVERNMENT POLYTECHNIC RANCHI", branch:"COMPUTER SCIENCE AND ENGINEERING (CSE)"},
  // … Add the rest here …
];

const startDate = "10th June 2025";
const endDate   = "25th July 2025";

function verify(){
  const id = document.getElementById('certId').value.trim();
  const res = document.getElementById('result');
  const cert = certData.find(c => c.id === id);
  if(cert){
    res.innerHTML = `
      <h2 class="verified">✅ Certificate Verified</h2>
      <div class="field"><strong>Certificate No:</strong> ${cert.id}</div>
      <div class="field"><strong>Student Name:</strong> ${cert.name}</div>
      <div class="field"><strong>Project Name:</strong> ${cert.project}</div>
      <div class="field"><strong>College:</strong> ${cert.college}</div>
      <div class="field"><strong>Branch:</strong> ${cert.branch}</div>
      <div class="field"><strong>Internship Duration:</strong> ${startDate} – ${endDate}</div>
    `;
  }else{
    res.innerHTML = `<h2 class="notfound">❌ Certificate not found</h2>`;
  }
}
</script>
</body>
</html>
