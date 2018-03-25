## Configuring Views Relationships

Let's say you have a View that's pulling in content. Let's say you want to have that View pull in other content \(content that is not available in the, for example, Content type of Job Posting. This content could be a contact person. The contact person is not a field in the Job Posting content type, instead it's pulled in as a reference into the Job Posting content type.

This is a useful setup as the contact person could then update their information in one place and it would automatically be updated in all Job Postings he's tagged in.

However since he's not fieldable within the Job Posting content type we can't just add him in a new field. That's why we'd using Views Relationships.

To setup the Relationship:

* Under Advanced select Add next to Relationships.
* Select the desired field.
* In the Fields section in the first column of the Views page you'll now be able to add the Content pulled in through the Reference.



