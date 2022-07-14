<script lang="ts">
    import Chart from 'chart.js/auto/auto.esm';
    import { onMount } from 'svelte';

    let chartRef: HTMLCanvasElement;

    // following code is working with:
    // @sveltejs/kit: 1.0.0-next.372
    // vite: 2.9.14
    onMount(() => {
        new Chart(chartRef, {
            type: 'line',
            data: {
                labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
                datasets: [{
                    label: 'My First dataset',
                    backgroundColor: 'rgb(255, 99, 132)',
                    borderColor: 'rgb(255, 99, 132)',
                    data: [0, 10, 5, 2, 20, 30, 45]
                }]
            },
            options: {
                scales: {
                    yAxes: [{
                        ticks: {
                            beginAtZero: true
                        }
                    }]
                }
            }
        });
    });
</script>

<canvas bind:this={chartRef} />
