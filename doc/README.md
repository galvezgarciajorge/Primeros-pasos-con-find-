# Proyecto  de consultas

Consultaremos el Base de datos de bdgame con el *find()*

    * Consultas find()
   

    ¡[Consulta 1]

    ***La consulta es de nombre.***

    > db.bdgame.find ({"nombre": "Minecraft"})
{ "_id" : ObjectId("5f9b2ff8c0865b2b3558ec4e"), 
"nombre" : "Minecraft", "recaudacion" : [ "88.700.000" ], 
"compañia" : "Mojang AB", 
"tipo" : [ "Sandbox", "Construccion" ], 
"estreno" : 0.0008145164939590028, 
"dificultad" : "*" }

     ¡[Consulta 2]
     
     ***La consulta por lista.***

> db.bdgame.find ({"nombre": "Age of Empires"}).pretty()
{
        "_id" : ObjectId("5f9b2ff8c0865b2b3558ec51"),
        "nombre" : "Age of Empires",
        "recaudacion" : [
                "215.000.000"
        ],
        "compañia" : "Ensemble Studios",
        "tipo" : [
                "Estrategia",
                "Construccion"
        ],
        "estreno" : 0.001301952929394091,
        "dificultad" : "***"
    ***La consulta es nombre y pero con pretty (Ordenado en lista).***

    ¡[Consulta 3]

    ***Hacemos dos consulta sobre producto en lista.***
    
    > db.bdgame.find ({"nombre":"League of Legends","recaudacion":"21.500.000"}).pretty()
{
        "_id" : ObjectId("5f9b2ff8c0865b2b3558ec50"),
        "nombre" : "League of Legends",
        "recaudacion" : [
                "21.500.000"
        ],
        "compañia" : "Riot Games",
        "tipo" : [
                "Batalla",
                "Estrategia"
        ],
        "estreno" : 0.001443504230960677,
        "dificultad" : "****"

    ¡[Consulta 4]

    ***Es una multiconsulta de filtrado.***
    
    > db.bdgame.find ({"compañia":"Blizzard"},{"tipo":1, "dificultad":"****"}).pretty()                    
{
        "_id" : ObjectId("5f9984d01c0210b975700d1c"),
        "tipo" : [
                "Disparos",
                "Accion"
        ],
        "dificultad" : "****"
}
{
        "_id" : ObjectId("5f9984d01c0210b975700d1e"),
        "tipo" : [
                "Batalla",
                "Estrategia"
        ],
        "dificultad" : "****"
}
{
        "_id" : ObjectId("5f9b2ff8c0865b2b3558ec4d"),
        "tipo" : [
                "Disparos",
                "Accion"
        ],
        "dificultad" : "****"
}
{
        "_id" : ObjectId("5f9b2ff8c0865b2b3558ec4f"),
        "tipo" : [
                "Batalla",
                "Estrategia"
        ],
        "dificultad" : "****"

    ¡[Consulta 5]

    ***Consulta de conteo de datos.***
    
    > db.bdgame.count()                                                                
13

    ¡[Consulta 6]

    ***Consulta que devuelve todos los datos de dos producto del mismo tipo.***
    
    > db.bdgame.find ().limit(2) 
{ "_id" : ObjectId("5f9984cf1c0210b975700d1b"), "nombre" : "Counter-Strike", "recaudacion" : "258M", "compañia" : "VALVE Software", "tipo" : [ "Disparos", "Accion" ], "estreno" : "19/06/1999", "dificultad" : "****" }
{ "_id" : ObjectId("5f9984d01c0210b975700d1c"), "nombre" : "Overwatch", "recaudacion" : "585.60M", "compañia" : "Blizzard", "tipo" : [ "Disparos", "Accion" ], "estreno" 
: "24/05/2016", "dificultad" : "**" }
