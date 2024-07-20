# hospitality-process-digitalization
[9:31 am, 16/7/2024] .: <!DOCTYPE html>
<html>
<head>
    <title>Hospitality Process Digitalization</title>
</head>
<body>
    <h1>Upload Group and Hostel Information</h1>
    <form id="uploadForm">
        <label for="groupFile">Group Information CSV:</label>
        <input type="file" id="groupFile" name="groupFile" accept=".csv" required><br><br>
        <label for="hostelFile">Hostel Information CSV:</label>
        <input type="file" id="hostelFile" name="hostelFile" accept=".csv" required><br><br>
        <button type="submit">Upload</button>
    </form>
    <div id="results"></div>
    <button id="downloadBtn" style="display:none;">Download CSV</button>
    <script src="app.js"></script>
</body>
</html>
[9:31 am, 16/7/2024] .: from flask import Flask, request, jsonify, send_file
import csv
import os

app = Flask(_name_)

@app.route('/upload', methods=['POST'])
def upload_files():
    group_file = request.files['groupFile']
    hostel_file = request.files['hostelFile']
    group_data = parse_csv(group_file)
    hostel_data = parse_csv(hostel_file)
    allocation = allocate_rooms(group_data, hostel_data)
    save_allocation_to_csv(allocation)
    return jsonify(allocation)

def parse_csv(file):
    # Parse CSV file and return data
    pass

def allocate_rooms(group_data, hostel_data):
    # Room allocation logic
    pass

def save_allocation_to_csv(allocation):
    # Save allocation results to CSV
    pass

if _name_ == '_main_':
    app.run(debug=True)
