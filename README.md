# mern-classwork-pokedex

### Make Sure You Hanve the Following Checked out:

Server - https://github.com/cs-fullstack-master/mern-pokedex-backend.git
Client - https://github.com/cs-fullstack-master/mern-pokedex-frontend.git

* Add a method to server to get one Pokemon by it's number

* Modify the client CSS to format Pokemon names with initial caps


//Get Pokemon by ID
router.get('/find/:id',(req, res) => {
    let newId = ('https://pokeapi.co/api/v2/pokemon/'+req.params.id);
    console.log("new id is here: "+newId);
    request(newId.findById({id: req.params.id}, function (err, response, body) {
        if (err) {
            throw err; // If we get an error then bail
        }
        // Use Express to send the JSON back to the client in the web response
        let jsonResp = JSON.parse(body);
        // console.log(setPokemons(jsonResp.id));
        res.send(jsonResp);

    }));
});
