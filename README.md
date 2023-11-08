Funcion crearePokemonCard
Esta función esta diseñada pra crear una tarjea de cada Pokemon basada en una API de pokeapi.co. Cada tarjeta contiene información como: nombre, imagen, el id y el tipo de pokemon. Todas las tarjetas se ajustan al estilo definido en el CSS.

Esta función se  invoca con un objeto llamado "pokemon" que contiene los datos de cada pokemon que se va a mostrar en la tajeta. La funcion se ejecuta en los siguientes pasos:

- Crea un elemento div para representar la tarjeta de cada pokemon.
  
        const pokemonElement = document.createElement('div');
    
- Determina el tipo de pokemon a partir de los datos proporcionados en el objeto  "pokemon".
  
        const type = pokemon.types[0].type.name;
    
-Asigna un background a la tarjeta de cada pokemon dependiendo del tipo de pokemon. Los colores estan predefinidos en un objeto llamado "colors".
    const color = colors[type];
    pokemonElement.style.backgroundColor = color;
    
- Obtiene el ID, el nombre y el tipo de pokemon desde el objeto "pokemon".
  
        const pokemonId = pokemon.id;
        const pokemonName = pokemon.name;
        const typeName = pokemon.types[0].type.name;
 
-Genera el contenido HTML de la tarjeta de Pokemon utilizando los datos obtenidos.

    pokemonElement.innerHTML = `
    <div class="img-container">
		<img src=" https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${pokemonId}.png" alt="${pokemonName}">
		
    </div>
    <div class="info">
        <span class="number">${pokemonId.toString().padStart(4, '#00')}</span>
        <h3 class="name">${pokemonName}</h3>
        <small class="Type">Tipo: <span>${typeName}</span></small>
    </div>
    `;




El ID del Pokemon se formatea con ceros a la izquierda para que tenga un ancho fijo de 4 caracteres.

    <span class="number">${pokemonId.toString().padStart(4, '#00')}</span>

La imagen del Pokemon se obtiene del siguiente repositorio utilizando su ID para identificar la imagen por su nombre y .png
https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon
    
