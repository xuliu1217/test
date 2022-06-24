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
- @GetMapping: map to a get request
- @PathVariable: a part of the url path
```
@GetMapping("/{id}")
    public ResponseEntity<PostDto> getPostById(@PathVariable(name = "id") long id)
```
- @RequestParam: parameter of request body. In the url, begin with "?"
```
public PostResponse getAllPosts(
            @RequestParam(value = "pageNo", defaultValue = AppConstants.DEFAULT_PAGE_NUMBER, required = false) int pageNo,
            @RequestParam(value = "pageSize", defaultValue = AppConstants.DEFAULT_PAGE_SIZE, required = false) int pageSize,
            @RequestParam(value = "sortBy", defaultValue = AppConstants.DEFAULT_SORT_BY, required = false) String sortBy,
            @RequestParam(value = "sortDir", defaultValue = AppConstants.DEFAULT_SORT_DIR, required = false) String sortDir
    )
```
- @PutMapping: map to a put request
```
@PutMapping("/{id}")
    public ResponseEntity<PostDto> updatePostById(@RequestBody PostDto postDto, @PathVariable(name = "id") long id){}
```
- @DeleteMapping: map to a delete request
```
@DeleteMapping("/{id}")
    public ResponseEntity<String> deletePost(@PathVariable(name = "id") long id){}
```
- @ResponseStatus: response status

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
