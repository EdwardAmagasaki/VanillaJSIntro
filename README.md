
# Introdução ao JavaScript Vanilla

JavaScript é uma das linguagens de programação mais populares e versáteis, amplamente utilizada para o desenvolvimento de aplicações web. Com JavaScript, você pode criar desde simples interações em páginas web até complexas aplicações de uma única página (SPA).

Neste post, vamos criar uma aplicação simples que exibe uma lista de itens categorizados, utilizando JavaScript Vanilla.

## Estrutura do Projeto

### HTML

**HTML**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista de Itens</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <table id="example">
        <thead>
            <tr>
                <th>Nome</th>
                <th>Categoria</th>
            </tr>
        </thead>
        <tbody>
            <!-- Conteúdo será inserido aqui -->
        </tbody>
    </table>
    <script src="script.js"></script>
</body>
</html>
```

### JavaScript

**JavaScript**

```javascript
document.addEventListener('DOMContentLoaded', function() {
    const categorias = [
        { id: 1, nome: 'Eletrônicos' },
        { id: 2, nome: 'Moda' }
    ];

    const itens = [
        { id: 1, nome: 'Smartphone XYZ', categoriaId: 1 },
        { id: 2, nome: 'Fone de Ouvido ABC', categoriaId: 1 },
        { id: 3, nome: 'Camisa Estilosa', categoriaId: 2 },
        { id: 4, nome: 'Tênis Confortável', categoriaId: 2 }
    ];

    const tabela = document.querySelector('#example tbody');

    itens.forEach(item => {
        const categoria = categorias.find(cat => cat.id === item.categoriaId);
        const row = document.createElement('tr');
        row.innerHTML = `<td>${item.nome}</td><td>${categoria.nome}</td>`;
        tabela.appendChild(row);
    });
});
```

### CSS

**CSS**

```css
table {
    width: 100%;
    border-collapse: collapse;
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
}

th {
    background-color: #f2f2f2;
}
```
