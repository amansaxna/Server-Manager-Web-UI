# REST API  
### Consuming a RESTful Web Service with AJAX-Bootstraping
A basic WEB UI frontend for an application created using   **Bootstrap** framework.Using **AJAX** methods to create, show and delete records from the UI : 
	![GitHub site_home](src/images/site_home.png)
* #### Show All servers :-
	 Displays all the servers if no parameters are passed.When server id is passed as a parameter - return a single server or 404 if there’s no such a server.
 ```javascript
		        var xhttp = new XMLHttpRequest();
			//formatting data
			xhttp.open("GET", "http://localhost:8011/restapi/get_servers", true);
			xhttp.setRequestHeader("Content-type", "application/json"); 
			xhttp.send();
```
![GitHub site_show_all](src/images/site_show_all.png)
* #### Insert a Server :-
The server object is passed as a json-encoded message body. Here’s an example:<br />
 ```javascript
		      	var xhttp = new XMLHttpRequest(); 
		        var url =   document.url_input.name.value + "-";
		          url = url + document.url_input.id.value + "-";
		          url = url + document.url_input.language.value + "-"; 
		          url = url + document.url_input.framework.value  ;
		        xhttp.open("PUT", "http://localhost:8011/restapi/get_servers/"+url, true);
		        xhttp.send();
```
![GitHub site_insert](src/images/site_insert.png)
```BSON
		{ 
			“name”: ”my centos”,
		 	“id”: “123”,
		  	“language”:”java”,
		   	“framework”:”django” 
		}
```
* #### Delete Server:-<br />
	 The parameter is a server ID. 
 ```javascript
		       var xhttp = new XMLHttpRequest(); 
		       xhttp.open("DELETE", "http://localhost:8011/restapi/get_servers/"+id, true);
		       xhttp.send();
```

![GitHub site_show_all](src/images/site_show_all.png)
* #### Find Servers by Name/ ID :-<br />
	 The parameter is a string. Checks if a server name contains this string and return one or more servers found. Return 404 if nothing is found.
	 ![GitHub search_by_id](src/images/search_by_id.png)