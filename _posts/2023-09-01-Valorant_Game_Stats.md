---
toc: true
comments: True 
layout: default
title: Valorant Statistics
description: The statistics for all the competitive valorant games I play
type: hacks
courses: { compsci: {week: 2} }
---
# Valorant Competitive Statistics

<head>
    <!-- load jQuery and DataTables output style and scripts -->
    <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.13.4/css/jquery.dataTables.min.css">
    <script type="text/javascript" language="javascript" src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script>var define = null;</script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/1.13.4/js/jquery.dataTables.min.js"></script>
</head>

<style>
    .table {
        color: #eeeeee;
    }
    th {
        color: #dddddd;
    }

    * {
        color: #dddddd;
     }
</style>
<!-- Body contains the contents of the Document -->
<body>
    <table id="demo" class="table">
        <thead>
            <tr>
                <th>Map</th>
                <th>Agent</th>
                <th>K/D</th>
                <th>Leaderboard Place</th>
                <th><span style="color: green;">Win</span> or <span style="color: red;">Loss</span></th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Lotus</td>
                <td>Skye</td>
                <td>0.4</td>
                <td>10th</td>
                <td><span style="color: red;"><span style="color: red;">Loss</span></span></td>
            </tr>
            <tr>
                <td>Haven</td>
                <td>Brim</td>
                <td>0.8</td>
                <td>6th</td>
                <td><span style="color: red;">Loss</span></td>
            </tr>
            <tr>
                <td>Fracture</td>
                <td>Skye</td>
                <td>0.8</td>
                <td>9th</td>
                <td><span style="color: red;">Loss</span></td>
            </tr>
            <tr>
                <td>Fracture</td>
                <td>Skye</td>
                <td>0.7</td>
                <td>7th</td>
                <td><span style="color: red;">Loss</span></td>
            </tr>
            <tr>
                <td>Split</td>
                <td>Skye</td>
                <td>1.4</td>
                <td>3rd</td>
                <td><span style="color: green;">Win</span></td>
            </tr>
            <tr>
                <td>Pearl</td>
                <td>Chamber</td>
                <td>1.1</td>
                <td>5th</td>
                <td><span style="color: green;">Win</span></td>
            </tr>
            <tr>
                <td>Split</td>
                <td>Skye</td>
                <td>0.9</td>
                <td><span style="color: yellow;">MVP</span></td>
                <td><span style="color: green;">Win</span></td>
            </tr>
            <tr>
                <td>Pearl</td>
                <td>Chamber</td>
                <td>2.7</td>
                <td>3rd</td>
                <td><span style="color: green;">Win</span></td>
            </tr>
            <tr>
                <td>Ascent</td>
                <td>Skye</td>
                <td>0.9</td>
                <td>5th</td>
                <td><span style="color: green;">Win</span></td>
            </tr>
            <tr>
                <td>Bind</td>
                <td>Skye</td>
                <td>0.9</td>
                <td>3rd</td>
                <td><span style="color: green;">Win</span></td>
            </tr>
            <tr>
                <td>Lotus</td>
                <td>Brim</td>
                <td>0.6</td>
                <td>7th</td>
                <td><span style="color: red;">Loss</span></td>
            </tr>
        </tbody>
    </table>
</body>

<!-- Script is used to embed executable code -->
<script>
    $("#demo").DataTable();
</script>