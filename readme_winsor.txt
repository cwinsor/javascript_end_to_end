from  https://mherman.org/blog/postgresql-and-nodejs/

This is an example frontend/backend javascript web app with postgres on the backend.  It uses express web server/routing and (a little) angular on the front-end.
Anyway it s a good example.
INTERESTING - the example is almost entirely straight out of the node "express-generator". More specifically - THERE IS NO GITHUB!  There is hardly any code added by the author, and what code is added just copy from the website.   I have included my work as "MINE" as an example - you should follow the instructions and MAKE-YOUR-OWN :)

npm install -g express-generator@4.13.4
express node-postgres-todo
cd node-postgres-todo
npm install

if you don't have "npm" then you need to install node.  Continuing on...

node bin/www         (note for clarity "www" is a regular javascript file - nothing special - would be better named www.js)
and visit  http://localhost:3000/

ok..... the code...
there is client-side and server-side code...

--- client-side ---
client-side... unfortunately it is muddled with "jade"
views/*.jade

--- server-side ---
app.js     this sets up a bunch of global shit including "app" which is express

www        aaaaaaaaargh  -- this is JAVASCRIPT and should be named www.js
      creates express server
      listens on the postgres

routes/index.js
    this routes        get('/'
    later we will add  get('/api/v1/todos'
routes/users.js
    (unclear what this is for...)

models/database.js      this does  const pg = require('pg');     i.e. it created a global "pg"

==========================================

add the models/database.js as instructed

==========================================
confirm that postgres is up and running.  If not you need to install postgres and play with pgadmin.

For USERNAME/PASSWORD:  "pg" will look for environment variables for these.  In windows do the following:

$env:PGUSER='postgres'
$env:PGHOST='localhost'
$env:PGPASSWORD='supersecretpassword'
$env:PGDATABASE='todo'
$env:PGPORT='3000'

Continuing from there...

Add the "todo" database as instructed
create the table as instructed
add some entries to the table

You should now be able to do a  http://localhost:3000/api/v1/todos  and http "get" your data

==========================================

now the tutorial proceeds to add client-side "Angular"...

public/javascript/app.js       this defines the angular "module"  ....   "get", "post", "delete"  on client-side
index.html                     this defines the angular "view"    ....   defines a list for 'get'    ng-app,  ng-controller,  ng-repeat to make a list

the tutorial then gives final code (cleaned up).
and THIS is where we leave the project.

NEXT STEP is to REFACTOR the code.  I am making a commit at this point.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx



