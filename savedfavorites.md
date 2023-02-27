<html>
<head>
    <title>My Favorites</title>
</head>
<body>
    <h1>My Favorites</h1>
    <ul id="favorites-list"></ul>
    <script>
        // Make a GET request to the API endpoint to retrieve the list of favorites
        fetch('http://127.0.0.1:8086/api/favorites/favorites/all')
            .then(response => response.json())
            .then(favorites => {
                // Add each favorite to the list on the HTML page
                const favoritesList = document.getElementById('favorites-list');
                favorites.forEach(favorite => {
                    const listItem = document.createElement('li');
                    listItem.textContent = `${favorite.title} - Ingredients: ${favorite.ingredients}, Instructions: ${favorite.instructions}`;
                    favoritesList.appendChild(listItem);
                });
            })
            .catch(error => console.error(error));
    </script>
</body>
</html>