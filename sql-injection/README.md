# SQL Injection Cheatsheet

[Original Link](https://portswigger.net/web-security/sql-injection/cheat-sheet "cheat sheet sql injection")

> This SQL injection cheat sheet contains examples of useful syntax that you can use to perfrom a variety of tasks that often arise when performing SQL injection attacks.

# String Concatenation

> You can concatenate together multiple strings to make a single string.

**Oracle** :: 'foo'||'bar'                                          <br>
**Microsoft** :: 'foo'+'bar'                                        <br>
**PostgreSQL** :: 'foo'||'bar'                                      <br>
**MySQL** :: 'foo' 'bar' [Note the space between the two strings]   <br>
**MySQL** :: CONCAT('foo','bar')                                    <br>

# Substring

> You can extract part of a string, from a specified offset with a specified length. Note that the offset index is 1-based. Each of the following expressions will return the string ba.

**Oracle** :: SUBSTR('foobar', 4, 2)        <br>
**Microsoft** :: SUBSTRING('foobar', 4, 2)  <br>
**PostgreSQL** :: SUBSTRING('foobar', 4, 2) <br>
**MySQL** :: SUBSTRING('foobar', 4, 2)      <br>

# Comments

> You can use comments to truncate a query and remove the portion of the original query that follows your input.

**Oracle** :: --comment                                         <br>
**Microsoft** :: --comment                                      <br>
**Microsoft** :: /✶comment✶/                                    <br>
**PostgreSQL** :: --comment                                     <br>
**PostgreSQL** :: /✶comment✶/                                   <br>
**MySQL**	:: #comment                                           <br>
**MySQL**	:: /✶comment✶/                                        <br>
**MySQL**	:: -- comment [Note the space after the double dash]  <br>

# Database version

> You can query the database to determine its type and version. This information is useful when formulating more complicated attacks.

**Oracle**  :: SELECT banner FROM v$version   <br>
**Oracle**  :: SELECT version FROM v$instance <br>
**Microsoft** :: SELECT @@version             <br>
**PostgreSQL** :: SELECT version()            <br>
**MySQL** :: SELECT @@version                 <br>

# Database contents

> You can list the tables that exist in the database, and the columns that those tables contain.

**Oracle** :: SELECT * FROM all_tables                                                          <br>
**Oracle** :: SELECT * FROM all_tab_columns WHERE table_name = 'TABLE-NAME-HERE'                <br>
**Microsoft** :: SELECT * FROM information_schema.tables                                        <br>
**Microsoft** :: SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'  <br>
**PostgreSQL** :: SELECT * FROM information_schema.tables                                       <br>
**PostgreSQL** :: SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE' <br>
**MySQL** :: SELECT * FROM information_schema.tables                                            <br>
**MySQL** :: SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'      <br>

