# Chart.js

1. **Download Chart.js**: Go to: https://github.com/chartjs/Chart.js/releases or use npm:

```bash
npm install chart.js

```

2. **Include Chart.js into the project**:

```html
<script src="path/to/Chart.js"></script>
```

3. **Create a Canvas Element**:

```html
<canvas id="myChart" width="400" height="400"></canvas>
```

4. **Write JavaScript to Create the Chart**: 

```html
<script>
    var ctx = document.getElementById('myChart').getContext('2d');
    var myChart = new Chart(ctx, {
        type: 'line',
        data: {
            labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
            datasets: [{
                label: 'My Dataset',
                data: [10, 20, 30, 40, 50, 60, 70]
            }]
        },
        options: {
            // Add options here if needed
        }
    });
</script>
```
