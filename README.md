README
======

This app demonstrates the accumulation of single-use prepared statements on each db connection in ActiveRecord when some types of queries are used.

Just visit `/posts` and refresh the page and you should see a list of prepared statements at the bottom of the page, which will grow with each request.

With apps scaled out to several application servers, each with lots of worker processes, you can quite easily have hundreds of connections, and if each of them is using a pool of 1000 prepared statements the db will likely run out of memory.
