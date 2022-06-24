1. List all of the new annotations to your annotaitons.md and explain its role.
- Please see the annotation.md

2. What is DTO, VO, Payload, DO?
- DTO stands for Data Transfer Object, which transfer data to remote interfaces, just like web services. It is a class in Java, and the definition of the class need to correspond to the data in request body. This pattern fits very well in a REST API and DTOs will give you more flexibility in the long run. Which decouple persistence models from API models
- VO means value objects.It is a special type of object that can hold values such as java.lang.Integer and java.lang.Long.A VO should always override the equals() and hashCode() methods. VOs generally encapsulate small objects such as numbers, dates, strings, and more.
- Payload is the essential information in a data block that you send to or receive from the server when making API requests. The Payload can be sent or received in a variety of formats, including JSON.
- Do is DTO.

3. @RestController annotation is a combination of 2 annotations, what is that? List an example how to use the 2 annotations.
- @RestController eliminates the need to annotate every request handling method of the controller class with the @ResponseBody annotation
- The two annotations are @Controller and @ResponseBody
```
@Controller
@RequestMapping("posts")
  public class SimplePostController {

      @GetMapping("/{id}")
      public @ResponseBody Post getPost(@PathVariable int id) {
          return findPostById(id);
      }

     
  }
```
4. Does by default all the methods of JpaRepository are Transactional?
- Only CRUD methods are by default marked as transactional. If we want to use custom query methods, we need mark it with @Transactional.

5. What is Transactional(@transactional)?
- It is one of the most essential parts of Spring MVC.It provides broad support for transaction management and allows developers to concentrate on business logic rather than worrying about data integrity in the event of system failures

6. SimpleJpaRepository is the default implementation class of the JpaRepository interface? Could you find it in resource code?
- In windows, Ctrl + click the left of the mouse.
```
public interface JpaRepository<T, ID> extends PagingAndSortingRepository<T, ID>, QueryByExampleExecutor<T> {
    List<T> findAll();

    List<T> findAll(Sort sort);

    List<T> findAllById(Iterable<ID> ids);

    <S extends T> List<S> saveAll(Iterable<S> entities);

    void flush();

    <S extends T> S saveAndFlush(S entity);

    <S extends T> List<S> saveAllAndFlush(Iterable<S> entities);
```
7. Which media type or representational format we have used to exchange data between client and server?
- Json is common, but there are still others, such as html.

8. What is @Pathvariable and @RequestParam, and what is the difference?
- @PathVariable: is used to extract the value from the URI.It is a part of URL. It is most suitable for the RESTful web service where the URL contains some value. Spring MVC allows us to use multiple @PathVariable annotations in the same method. A path variable is a critical part of creating rest resources.
- @RequestParam can bind a web request parameter to a method parameter. A good example is the use of paging, in url, it usually apprear after "?".It has the following part:defaultValue (used as a fallback when the request parameter is not provided or has an empty value); value (name of the request parameter to bind to).
- The @RequestParam is used to extract query parameters while @PathVariable is used to extract data right from the URI.
9. do you know @RequestMapping(value = "/users", method = RequestMethod.POST) ? could you list CRUD use this style?
- @RequestMapping(value = "/posts", method = RequestMethod.GET)
- @RequestMapping(value = "/posts/{id}", method = RequestMethod.GET)
- @RequestMapping(value = "/posts", method = RequestMethod.POST)
- @RequestMapping(value = "/users/{id}", method = RequestMethod.PUT)
- @RequestMapping(value = "/users/{id}", method = RequestMethod.DELETE)

