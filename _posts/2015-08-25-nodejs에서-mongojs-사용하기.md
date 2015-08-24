---
layout: post
title: Nodejs에서 mongojs 사용하기
categories: ["Nodejs"]
tags: ["mongojs", "nodejs"]
published: True

---

mongo client로 사용하기 위한 패키지를 몇 가지 보았는데, [mongojs](https://github.com/mafintosh/mongojs)가 가장 사용법이 단순한 것 같아 선택하였다.

설치는 역시 npm을 사용하면 된다.


	npm install mongojs --save


사용방법이 정말 단순하다. `connectionString` 은 접속 url인데, [다양한 형태](http://docs.mongodb.org/manual/reference/connection-string/)로 작성 가능하다.


	var mongojs = require('mongojs');
	var db = mongojs(connectionString, [collections]);




여기서 나온 db object의 property 접근으로 collection을 가져올 수 있다.


	db.mycollection.find({name: 'test'}, function (err, data) {
		// process with err, data
	});


주로 사용하는 API들은 [이 곳](https://github.com/mafintosh/mongojs#api)에 정리되어 있다.

