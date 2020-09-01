* For the foos property requirement `foos (array of Ids; an array of unique foo document Ids associated with this document)`, I was thinking about adding a check to verify that the FooId added to this array exists, similar to a FK constraint, but didn't for two reasons:
  * Couldn't come up with an elegant solution other than making another query to the database to check for existing documents
  * We could still get into a state of inconsistent data if we deleted an object after it was added to another object. It thus seemed given our database choice, this wasn't a priority.
=> I see the second reason is asked as a solve in a bonus. From reading into Mongoose, it seems like the right thing to do would be to add a middleware hook. Couldn't quite get a working solution with that so elected to add it into the controller where it removed self references.
* It took me some to get the POST and PUT body to function properly. I'm not well-versed in Express and didn't realize we needed to add `app.use(express.json());` into `root.test.js`.
* Didn't attempt to add the autogenerated documentation as I'm not too familiar with Express, and felt wouldn't be able to get a satisfactory solution quickly.