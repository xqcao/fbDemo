
/**
 * Module dependencies.
 */

var express = require('express');
//var routes = require('./routes');
//var user = require('./routes/user');
var http = require('http');
var path = require('path');

var app = express();

// all environments
app.set('port', process.env.PORT || 8000);
app.set('views', path.join(__dirname, 'views'));
app.set('view engine', 'hjs');
app.use(express.favicon());
app.use(express.logger('dev'));
app.use(express.json());
app.use(express.urlencoded());
app.use(express.methodOverride());
app.use(app.router);
app.use(require('less-middleware')({ src: path.join(__dirname, 'public') }));
app.use(express.static(path.join(__dirname, 'public')));

// development only
if ('development' == app.get('env')) {
  app.use(express.errorHandler());
}

function showfb1(tempnum){
	var str1 = "";
	for(var i = 0; i < tempnum; i++){
		str1 += "fibonacci< "+ i +" >  = "+ fb(i) +"\n\n";
		

  	}
	return str1;
}

function fb(n) {
	if(n <2) {
		return 1;
	} else {
		return fb(n-1)+fb(n-2);
	}
};

app.get('/',function(req,res){
	res.render("index.hjs",{abc: "please input the number"+"\n"});
});

app.post('/login',function(req,res){
	//res.render("home.jade",{title: "building my web apps in node with Express"});
	//res.render("index.hjs",{abc: showfb1(20)+"\n"});
	res.render("index.hjs",{abc: showfb1(req.body.numbera)+"\n"});
});


http.createServer(app).listen(app.get('port'), function(){
  console.log('Express server listening on port ' + app.get('port'));
});
