# fullstack-backend
`[1] Go to start.spring.io, select Maven,Java, Spring Boot preselected option, name the project and select 17 for Java
`[2] Add Dependecies Spring Web,JPA and MySQL Driver and export, then extract the zip
`[3] Open Intellij and select the folder extracted
`[4] At .com... create packages: Controller, Exception, Model, Repository
`[5] At Model, create Java file and add @Entity at top of user , name User.Java, add Private id, username, name email, then use Getter Setters
`[6] Add Repository, add UserRepository.java file and choose interface, type public interface UserRepository extends JpaRepository<User,Long> 
`[7] At application properties type: spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://localhost:3306/Swam
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
`[8] Open MySQL, create Database (insert name) , then run the Intellij
`[9] In Controller create UserController java file, type @RestController
@CrossOrigin("/localhost:3000")
public class UserController {
    @Autowired
    private UserRepository userRepository;
    @PostMapping("/user")
    User newUser(@RequestBody User newUser){
        return userRepository.save(newUser);
    }
    @GetMapping("/users")
    List<User> getAllUsers(){
        return userRepository.findAll();

    }
}ty
`[10] Use postman, create new collection, name it, select POST, type http://localhost:8080/user, select body, raw,JSON, 
type:
{

"name":"Swam",
"username":"Htet",
"email":"swamhtetlin@gmail.com"

} and run
`[11] Play around with it with different inputs
`[12] Select GET, enter http://localhost:8080/users and run
<PAUSED HERE for now>
