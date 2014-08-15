can.list.bindingDemo
====================

a demo of can.js List binding 

```javascript
    $(function () {
        var data = new can.Model.List([
            {a: 1, b: 333, c: 'adasd'},
            {a: 2, b: 555, c: 'adfaf'},
            {a: 3, b: 666, c: 'adfa'},
            {a: 4, b: 777, c: 'sgfsgs'}
        ]);

        $('#container').html(
            can.view('tpl', {data: data})
        );

        $('a.add').click(function () {
            data.push({a: 1,b: 2,c: 3});
        })
    });



```html
    <script type='text/ejs' id='tpl'>
        <table class="table table-striped">
            <thead>
                <tr>
                    <td>A</td>
                    <td>B</td>
                    <td>C</td>
                </tr>
            </thead>
            <tbody>
                <% data.each(function(item) { %>
                <tr>
                    <td><%= item.a %></td>
                    <td><%= item.b %></td>
                    <td><%= item.c %></td>
                </tr>
                <% }); %>
            </tbody>
        </table>
    </script>
