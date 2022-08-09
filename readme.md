## MongoDB Mapper Reducer Program

Steps:

>> mongoimport persons.json -d test -c mapper --jsonArray

>> show dbs;

>> show collections;

>> db.mapper.aggregate([{$match: {gender: "male"}}]).pretty()

>> var mapper = function() { var person = emit(this.gender, this.age); $split: [person, ","]; };

>> var reducer = function(keyGender, valuesAge) { return valuesAge.length; };

>> dp.mapper.reducer(mapper, reducer, {out: "myoutput1"}) 
{"result":"myoutput1","ok":1}

>> show collections;

>> db.myoutput1.find()
