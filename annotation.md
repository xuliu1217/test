1. Controller
- @RestController: use it in all controller class.
- @RequestingMapping: followed by urn, show that it is a request.
```
@RestController
@RequestMapping("/api/v4/posts")
public class PostController{}
```
- @Autowired: with it, we don't need to create an instance mannually.
```
@Autowired
private PostService postService;

```
- @RequestBody: means that it will be mapping to a request body。
```
public ResponseEntity<PostDto> createPost(@RequestBody PostDto postDto) 
```
- @PostMapping: means that it will be mapping to a post request
```
 @PostMapping
    public ResponseEntity<PostDto> createPost(@RequestBody PostDto postDto)
```
2. Service
- @Service:use it in all Service class.
```
@Service
public class PostServiceImpl implements PostService
```
3. Dao- @Repository: use it in all Dao interface.
```
@Repository
public interface PostRepository extends CrudRepository<Post, Long>{}
```
4. Entity
- @Entity: use it in all entities for SQL.
- @Table: it will be mapping to a table in the database.
```
@Entity
@Table(
        name = "posts"
     //   uniqueConstraints = {@UniqueConstraint(columnNames =
     //   {"title"})}

)
```
- @Column: it will be mapping to a column in the database.
```
 @Column(name = "title", nullable = false)
        private String title;
```
- @Id: it will be mapping to the primary key.
```
@Id
@GeneratedValue(
                strategy = GenerationType.IDENTITY
        )
        private long id;
```
- @CreationTimestamp
- @UpdateTimestamp
```
 @CreationTimestamp
        private LocalDateTime createDateTime;
 @UpdateTimestamp
        private LocalDateTime updateDateTime;
```
- @Document: use it in all entities for mongodb.
```
@Document(collection = "posts")
public class Post 
```