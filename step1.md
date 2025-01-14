<!-- TOP -->
<div class="top">
  <img class="scenario-academy-logo" src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-2023.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Cassandra Query Language (CQL)</span>
    <span class="scenario-subtitle">ℹ️ For technical support, please contact us via <a href="mailto:academy@datastax.com">email</a>.</span>
  </div>
</div>

<!-- NAVIGATION -->
<div id="navigation-top" class="navigation-top">
 <a href='command:katapod.loadPage?[{"step":"intro"}]'
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
<span class="step-count"> Step 1 of 2</span>
 <a href='command:katapod.loadPage?[{"step":"step3"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>

<!-- CONTENT -->

<div class="step-title">Create and a keyspace and a table</div>

Welcome to the KillrVideo company! KillrVideo hired you to build the latest and greatest video sharing application on the Internet. Your task is to ramp up on the domain and become acquainted with Apache Cassandra. To start, you are looking into creating a table schema and to load some data.

The video metadata is made up of:

<table class="katapod-table">
  <tr>
    <th class="katapod-table">Column Name</th>
    <th class="katapod-table">Date Type </th>
  </tr>
  <tr>
    <td class="katapod-table">video_id</td>
    <td class="katapod-table">timeuuid</td>
  <tr>  
  <tr>
    <td class="katapod-table">added_date</td>
    <td class="katapod-table">timestamp</td>
  <tr>
    <tr>
    <td class="katapod-table">title</td>
    <td class="katapod-table">text</td>
  <tr>
</table>

<br>

✅ Use `nodetool` to verify that Cassandra is running (you may need to run this multiple times):
```
nodetool status
```

✅ Start the command line tool `cqlsh`:
```
cqlsh
```

✅ Create a keyspace called *killrvideo*. Use `SimpleStrategy` for the replication class with a replication factor of one.

<details class="katapod-details">
  <summary>Solution</summary>

```
CREATE KEYSPACE killrvideo
WITH replication = {
  'class':'SimpleStrategy', 
  'replication_factor': 1
};
```

</details>
<br>

✅ Switch to the newly created keyspace with the *Use* command:
<details class="katapod-details">
  <summary>Solution</summary>

```
use killrvideo;
```
</details>
<br>

✅ Create a table called `videos` with columns `video_id` of type `TIMEUUID`, `added_date` of type `TIMESTAMP` and `title` of type `TEXT`. Designate `video_id` as the primary key.

<details class="katapod-details">
  <summary>Solution</summary>

```
CREATE TABLE videos (
  video_id TIMEUUID,
  added_date TIMESTAMP,
  title TEXT,
  PRIMARY KEY (video_id)
);
```
</details>
<br>
<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"intro"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
 <a href='command:katapod.loadPage?[{"step":"step2"}]'
    class="btn btn-dark navigation-bottom-right">Next ➡️
  </a>
</div>
