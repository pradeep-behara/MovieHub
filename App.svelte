<script>
  import Imag from "./image.png";
  let da = {};
  let movie = "Scam 1992";
  // let hello = [10, 20];
  async function getData() {
    console.log("Hello ");
    const d = await fetch(
      "https://www.omdbapi.com/?t=" + movie + "&apikey=70541762"
    );
    const data = await d.json();
    // console.log(data);
    da = data;
    // console.log(da);
  }
</script>


<main>
<header>
  <img style="height:59px;width:60px"  src="{Imag}" alt="LOGO" width="20px" height="20px">
  <h1 style="color:red"><b>Movie Hub</b></h1>
  <marquee width="100%" direction="right"  height="100px"><h1>
<span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span><span>🎞🍟🍿🎬</span></h1></marquee>
</header>
<div class="first">
  <input bind:value={movie} type="text" placeholder="search a movie here">
  <button on:click={getData}>Click</button><br>
  </div>
  
  <div class="poster">
  {#if da.Poster}
  <img src="{da.Poster}" height="200px" width="200px" alt="{da.Title} Poster">
  {/if}
  </div>
  <div class="content">
  {#if da.Title}
  <table style="width:50%">
       <tr>
    <td><h3>Title</h3></td>
    <td><h3>{da.Title}</h3></td>
      </tr>

        <tr>
    <td><h3>Year</h3></td>
    <td><h3>{da.Year}</h3></td>
      </tr>

        <tr>
    <td><h3>Released</h3></td>
    <td><h3>{da.Released}</h3></td>
      </tr>

       <tr>
    <td><h3>Genre</h3></td>
    <td><h3>{da.Genre}</h3></td>
      </tr>

      <tr>
    <td><h3>Director</h3></td>
    <td><h3>{da.Director}</h3></td>
      </tr>

      <tr>
    <td><h3>Actors</h3></td>
    <td><h3>{da.Actors}</h3></td>
      </tr>

      <tr>
    <td><h3>Awards</h3></td>
    <td><h3>{da.Awards}</h3></td>
      </tr>

       <tr>
    <td><h3>Rating</h3></td>
    <td><h3>{da.imdbRating}</h3></td>
      </tr>

       <tr>
    <td><h3>Story</h3></td>
    <td><h3>{da.Plot}</h3></td>
      </tr>

  
      </table>

    
        

  {/if}
  </div>
  
 
</main>

<style>
  header {
    text-align: center;
  }
  marquee {
    color: white;
  }
  .first {
    text-align: center;
  }
  .poster {
    text-align: center;
    margin: 10px;
  }
  button {
    font-weight: bold;
    padding: 20px;
    padding-left: 20px;
    padding-right: 20px;
    padding-top: 10px;
    padding-bottom: 10px;
    text-align: center;
    border-radius: 10px;
    background-color: rgb(167, 172, 139);
    margin-left: 4px;
    border-color: black;
    border-width: 5px;
  }
  input {
    padding: 20px;
    width: 50%;
    font-size: 20px;
    padding-top: 10px;
    padding-bottom: 10px;
    border-radius: 10px;
  }
  main {
    background: linear-gradient(45deg);
    height: 200vh;
    background-color: rgb(28, 35, 47);
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }
  .content {
    color: white;
    text-align: center;
  }
  td {
    margin: 10%;
    text-align: left;
    padding: 10px;
    border: solid 1px white;
  }
  table {
    margin-left: 25%;
    border: solid 2px white;
    width: 50vh;
    font-family: monospace;
  }
  tr {
    border: solid 1px white;
    width: 150vh;
  }
  span {
    margin-left: 60px;
  }
</style>