<html>
    <head>
        <title>My Favorites</title>
        <style>
            @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
            body {
                font-family: 'Poppins', sans-serif;
                justify-content: center;
                align-items: center;
                display: flex;
                margin: 0px;
                padding: 0px;
            }
            .result {
                border-radius: 12px;
                border: 1px solid black;
                padding: 20px;
                max-width: 300px;
                flex-shrink: 0;
            }
            button {
                background-color: black;
                color: white;
                padding: 5px 10px;
                border-radius: 4px;
                border: none;
                margin-left: 10px;
                font-size: 16px;
            }
            button:hover{
                background-color: #FBFAF5;
                color: black;
                padding: 5px 10px;
                font-size: 16px;
                border-radius: 4px;
                border: none;
                margin-left: 10px;
            }
            li {
                margin-bottom: 30px;
                word-wrap: break-word;
            }
            ul {
                padding: 0px 20px;
            }
        </style>
    </head>
    <body>
        <h1>My Favorites</h1>
        <ul id="favorites-list"></ul>
        <script>
            // Make a GET request to the API endpoint to retrieve the list of favorites
            fetch('https://recipies.duckdns.org/api/favorites/favorites/all')
                .then(response => response.json())
                .then(favorites => {
                    // Add each favorite to the list on the HTML page
                    const favoritesList = document.getElementById('favorites-list');
                    favorites.forEach(favorite => {
                        const listItem = document.createElement('li');
                        const title = document.createElement('h2');
                        const ingredients = document.createElement('p');
                        const instructions = document.createElement('p');
                        const deleteButton = document.createElement('button');
                        deleteButton.textContent = 'Delete';
                        deleteButton.addEventListener('click', () => {
                            // Make a DELETE request to the API endpoint to delete the favorite
                            fetch(`https://recipies.duckdns.org/api/favorites/favorites/${favorite.title}`, {
                                method: 'DELETE'
                            })
                            .then(() => {
                                // Remove the deleted favorite from the list on the HTML page
                                favoritesList.removeChild(listItem);
                            })
                            .catch(error => console.error(error));
                        });
                        title.textContent = favorite.title;
                        ingredients.textContent = `Ingredients: ${favorite.ingredients}`;
                        instructions.textContent = `Instructions: ${favorite.instructions}`;
                        listItem.appendChild(title);
                        listItem.appendChild(ingredients);
                        listItem.appendChild(instructions);
                        listItem.appendChild(deleteButton);
                        favoritesList.appendChild(listItem);
                    });
                })
                .catch(error => console.error(error));
        </script>
    </body>
</html>