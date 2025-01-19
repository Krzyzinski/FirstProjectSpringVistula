# Project: FirstProjectSpringVistula

This project demonstrates a simple Spring MVC application with a controller handling HTTP requests and an example of rendering views using Thymeleaf. The application showcases the basic functionalities of the Spring framework.

## Project Structure


Controller Code

Package: com.example.FirstProjectSpringVistula1.Controller

```java
@Controller
//@RestController
public class HelloController {

    @GetMapping(value = "/")
    public String hello() {
        return "Hello Vistula, in my first Spring Controller";
    }

    @GetMapping("/greeting")
    public String greeting(@RequestParam(name="name", required=false, defaultValue = "World") String name, Model model) {
        model.addAttribute("name", name);
        return "greeting";
    }
    // http://localhost:8080/greeting?name=Vistula
}
```


# Thymeleaf View

The view file is located in the resources/templates directory as greeting.html and includes HTML code with dynamic content:
```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>
        Getting Started: Serving Web Content
    </title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'Hello, ' +${name} +'!'" />
<p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas vestibulum digissim malesuada.
</p>
<img th:src="@{/images/pies.jpg}" width="1280" height="720"/>
</body>
</html>
```
## Useing
1.Run application

2.Open a browser and test the application:


http://localhost:8080/ - Home page.

http://localhost:8080/greeting?name=Vistula - Dynamic Thymeleaf view.

# Goal
Demonstrate a simple web system with dynamic input handling and a view rendered using Thymeleaf.
