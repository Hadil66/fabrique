

<script>
export let data;
    console.log(data); // Hiermee kun je zien hoe de API-respons eruitziet
  
	import Search from '$lib/Search.svelte';
	let filterText = '';
</script>

<ul class="masonry">
    {#each data.artObjects as art}
        <li class="masonry-item">
            <figure>
                <img src={"https://fdnd-agency.directus.app/assets/" + art.image} alt={art.title} />
                <figcaption>
                    <h2>{art.title}</h2>
                    <a href="#" class="button">Meer info</a>
               </figcaption>
            </figure>

        </li>
    {/each}
    </ul>

<div class="wrap">
	<div class="search">
		<input
			type="text"
			class="searchTerm"
			bind:value={filterText}
			placeholder="Search the collection"
		/>
		<button type="submit" class="searchButton" aria-label="Submit search">
			<Search />
		</button>
	</div>
</div>

<style>
	* {
		transition: 0.2s;
		font-family: 'DIN Next', sans-serif;
	}
  
          .masonry {
            column-count: 1;
            column-gap: 1rem;
            list-style: none;
            padding: 0;
        }
    
        .masonry-item {
            break-inside: avoid;
            margin-bottom: 1rem;
            position: relative;
            overflow: hidden;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        figure{
            margin: 0;
            position: relative;
        }
    
        img {
            width: 100%;
            height: auto;
            display: block;
            border-radius: 8px;
            transition: transform 0.3s ease-in-out;
        }

        /* overlay */

        figcaption{
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }

        .masonry-item:hover img{
            transform: scale(1.1);
        }
        .masonry-item:hover figcaption{
            opacity: 1;
        }

        h2 {
            font-size: 16px;
            margin: 0.5rem 0;
        }

        a{
            color: black;
            background-color: #efc715;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            text-decoration: none;
            &:hover{
                background-color: #00b0f0;
            }
        }
    
        /* Grotere schermen: 2 kolommen voor medium en 3 voor grote schermen */
        @media (min-width: 600px) {
            .masonry {
                column-count: 2;
            }
        }
    
        @media (min-width: 900px) {
            .masonry {
                column-count: 3;
            }
            h2{
            font-size: 1.5rem;
            }
      }

	.search {
		width: 100vw;
		position: relative;
		display: flex;
	}

	.searchTerm {
		width: 100%;
		border: 2px solid black;
		border-right: none;
		padding: 0.5em 0 0 0.5em;
		color: #707070;
		font-size: 25px;
		text-decoration: underline black;
	}

	.searchTerm:focus {
		color: black;
	}

	.searchButton {
		width: 4em;
		height: 5.3em;
		padding: 0.5em;
		border-left: none;
		background: white;
		text-align: center;
		justify-content: center;
		color: black;
		cursor: pointer;
	}

	/*Resize the wrap to see the search bar change!*/
	.wrap {
		position: absolute;
		bottom: 0;
	}

	@media only screen and (min-width: 600px) {
		.wrap {
			position: absolute;
			bottom: 4em;
			left: 2em;
			right: 2em;
		}

		.search {
			width: 90vw;
			position: relative;
			display: flex;
		}
	}
</style>


