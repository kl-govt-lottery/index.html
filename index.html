<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lottery Admin Panel</title>
  <style>
    * { box-sizing: border-box; font-family: sans-serif; }
    body { background: #f4f6f8; margin: 0; padding: 20px; }
    .container { max-width: 600px; margin: auto; background: #fff; padding: 20px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
    h2 { text-align: center; margin-top: 0; color: #333; }
    .form-group { display: flex; gap: 10px; margin-bottom: 15px; }
    input { flex: 1; padding: 10px; border: 1px solid #ccc; border-radius: 4px; font-size: 14px; }
    button { padding: 10px 16px; background: #28a745; color: white; border: none; border-radius: 4px; cursor: pointer; font-weight: bold; }
    button:hover { background: #218838; }
    table { width: 100%; border-collapse: collapse; margin-top: 15px; }
    th, td { border: 1px solid #ddd; padding: 10px; text-align: left; }
    th { background: #007bff; color: white; }
    .btn-delete { background: #dc3545; padding: 5px 10px; font-size: 12px; }
    .btn-delete:hover { background: #c82333; }
    #status { font-size: 13px; color: #666; text-align: center; margin-top: 10px; }
  </style>
</head>
<body>

<div class="container">
  <h2>Lottery Admin Panel</h2>

  <form id="recordForm" class="form-group">
    <input type="text" id="ticketNo" placeholder="Ticket Number / Name" required>
    <input type="text" id="prize" placeholder="Prize (e.g. 1st, 2nd)" required>
    <button type="submit" id="addBtn">Add</button>
  </form>

  <div id="status">Data loading...</div>

  <table>
    <thead>
      <tr>
        <th>Ticket</th>
        <th>Prize</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody id="tableBody"></tbody>
  </table>
</div>

<script>
  const API_URL = "https://sheetdb.io/api/v1/osehsg02p213h";
  const statusDiv = document.getElementById("status");
  const tableBody = document.getElementById("tableBody");

  // 1. SheetDB se data load karna
  async function loadData() {
    statusDiv.innerText = "Sheet se data load ho raha hai...";
    try {
      const res = await fetch(API_URL);
      const data = await res.json();
      renderTable(data);
      statusDiv.innerText = "Data updated!";
    } catch (err) {
      statusDiv.innerText = "Error loading data: " + err.message;
    }
  }

  // 2. Table me data dikhana
  function renderTable(list) {
    tableBody.innerHTML = "";
    if (!list || list.length === 0) {
      tableBody.innerHTML = "<tr><td colspan='3' style='text-align:center;'>Koi record nahi hai</td></tr>";
      return;
    }

    list.forEach(item => {
      const row = document.createElement("tr");
      row.innerHTML = `
        <td>${item.ticket || item.Ticket || "-"}</td>
        <td>${item.prize || item.Prize || "-"}</td>
        <td>
          <button class="btn-delete" onclick="deleteRecord('${item.ticket || item.Ticket}')">Delete</button>
        </td>
      `;
      tableBody.appendChild(row);
    });
  }

  // 3. Naya record SheetDB par save karna
  document.getElementById("recordForm").addEventListener("submit", async function(e) {
    e.preventDefault();
    const ticket = document.getElementById("ticketNo").value.trim();
    const prize = document.getElementById("prize").value.trim();

    statusDiv.innerText = "Saving to Google Sheet...";
    try {
      await fetch(API_URL, {
        method: "POST",
        headers: {
          "Accept": "application/json",
          "Content-Type": "application/json"
        },
        body: JSON.stringify({
          data: [{ ticket: ticket, prize: prize }]
        })
      });

      document.getElementById("ticketNo").value = "";
      document.getElementById("prize").value = "";
      loadData();
    } catch (err) {
      statusDiv.innerText = "Save failed: " + err.message;
    }
  });

  // 4. Record delete karna
  async function deleteRecord(ticketValue) {
    if (!confirm("Kya aap ise delete karna chahte hain?")) return;
    statusDiv.innerText = "Deleting...";

    try {
      await fetch(`${API_URL}/ticket/${encodeURIComponent(ticketValue)}`, {
        method: "DELETE"
      });
      loadData();
    } catch (err) {
      statusDiv.innerText = "Delete failed: " + err.message;
    }
  }

  // Page start hote hi data pull karein
  loadData();
</script>

</body>
</html>
