---
layout: datatable
dataset_name: Median Income
---
Median household income data for the United States is from <a href="https://www.census.gov/data/tables/time-series/demo/income-poverty/historical-income-households.html">the US Census Bureau</a> Table H-8.

{% assign mydata=site.data.median_income %}



<table  class="table table-striped table-bordered" id="median_income">
    <caption>Median Income in 2018 Dollars</caption>
    <thead>
    {% for column in mydata[0] %}
        <th>{{ column[0] }}</th>
    {% endfor %}
    </thead>
    <tbody>
    {% for row in mydata %}
        <tr>
        {% for cell in row %}
            <td>{{ cell[1] }}</td>
        {% endfor %}
        </tr>
    {% endfor %}
    </tbody>
</table>


<script type="text/javascript">
    $(document).ready(function() {
        $('#median_income').DataTable(
            {
                paging: false,
                searching: false
            }
        );
    } );
</script>