# querycomment_plugin_java8

### Installation of the query comment jar file-

1. First keep the query comment jar file in one folder. And copy the path of the file this way, 
   E:\QueryCommentPlugin\QueryCommentPluginJava8
   
2. Now open the git bash here and type this command to install your jar file- 
```
mvn install:install-file -Dfile="E:\QueryCommentPlugin\QueryCommentPluginJava8\QueryCommentPluginJava8.jar" -DgroupId=org.devaten_team7.comment_plugin -DartifactId=comment_plugin -Dversion=1.0 -Dpackaging=jar
```
3. After type this command press enter and you will get the “Build Success” message it means that you have successfully installed the file.

4. For adding query comment through application you need to do the changes in the particular module repository. Where you want to add the following code.
   Do this changes in the repository file-<br />
   i) Add this import statement-
```
class="javapgm">import NamedJDBC.DevatenNamedParameterJdbcTemplate;
``` 
5. Replace this code with the matching this in your repository-
  
```
 @Repository
       public class FaqRepository1 extends JdbcDaoSupport {
          //private NamedParameterJdbcTemplate namedJdbcTemplate;
        DevatenNamedParameterJdbcTemplate namedJdbcTemplate;
        public FaqRepository1(DataSource dataSource){
        super.setDataSource(dataSource);
         //namedJdbcTemplate = new NamedParameterJdbcTemplate(dataSource);
          namedJdbcTemplate = new DevatenNamedParameterJdbcTemplate(dataSource);
        }
```        
6. Now add the dependency of this query comment plugin in your applications pom.xml file. 
   First open the pom.xml file of your application and paste this dependency in that and save it
```
<dependency>
          <groupId> org.devaten_team7.comment_plugin </groupId>                
          <artifactId>comment_plugin</artifactId>
         <version>1.0</version>
      </dependency>
```      
