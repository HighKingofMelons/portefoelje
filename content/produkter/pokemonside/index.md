---
Date: 2025-03-27
Title: Pokemonside
---

Pokemon

```JSX
import { Pokemon, Pokedex } from "pokeapi-js-wrapper";

export default async function PokemonEntry ({pokemonName}: {pokemonName: string}) {
    let pokedex = new Pokedex();

    let pokemon = await pokedex.getPokemonByName(pokemonName);

    return (
        <div>
            <h4>{pokemon.name}</h4>
            <h6>{(await pokedex.getPokemonSpeciesByName(pokemon.species.name)).flavor_text_entries.find((text) => text.language.name = "en")?.flavor_text}</h6>
        </div>
    )
}
```
