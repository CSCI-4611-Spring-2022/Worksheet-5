# Worksheet 5: Artistic Rendering

**Due: Thursday, April 7, 11:59pm CDT**

For the worksheets in this course, we will provide a Markdown template in a repository that will be created for you through GitHub classroom.  You can clone this repository, directly edit your local copy with your answers, and then commit and push the file to complete the submission.  Alternatively, you can use GitHub's built-in Markdown editor and edit directly on your repository website without having to clone it locally. 

*Do not make a copy of the provided Markdown template and submit that instead.* Our grading scripts will be looking for `README.md` within the root folder of your repository.  You should modify this template directly without changing the filename.



## Q1: Phong Shading

Given the following lighting equations:

​	ambient = k<sub>a</sub> * i<sub>a</sub>

​	diffuse = (n &middot; l) * k<sub>d</sub> * i<sub>d</sub>

​	specular = (n &middot; h) ^ s * k<sub>s</sub> * i<sub>s</sub>

​	color = ambient + diffuse + specular

Draw a picture that includes a point on a surface, a light, and labeled arrows for each vector that shows up in the equation.  Replace the image below with your diagram. 

*Hint: make sure that your vectors point in the right direction to make sense to calculate the dot products correctly!*

![replace this image with your diagram](./images/vectors.png)



## Q2 Silhouette Outline

In class, we will be talking in more detail about the key matrices used in vertex and fragment shaders. For example, we will learn that the `normalMatrix` must be used rather than the `modelMatrix` to transform normals to world space (or the combined `modelViewMatrix` to transform normals to eye/camera space).

 You will use the `normalMatrix`in all of the shaders that you write. However, the outline shader includes the most interesting use of normals.  Not only does each vertex have a normal, the shader also has access to the "left normal" for the normal of the triangle to the left and the "right normal" for the triangle to the right. As you can see in the assignment readme, these are used to determine whether the vertex lies on a silhouette edge. Here are a few questions about the logic you will need to use in that shader:

### Q2.1

Your outline vertex shader will need to include an if statement that is true if the vertex lies on a silhouette edge by testing the left normal and right normal in some way. You can assume the following:

- `vec3 e` is a vector calculated in eye/camera space that points from the vertex to the eye/camera 
- `vec3 nl` is defined for the left triangle normal 
- `vec3 nr` for the right triangle normal

Now, fill in the condition for the if statement.

*Hint: the solution is described in detail in the assignment readme file.*

```
if (/* --- Fill this in --- */)
```

### Q2.2

For the `nl` and `nr` that appear in your if statement above, should these two vectors be transformed to eye/camera space using the `normalMatrix`?

```
/* --- Write your answer here (yes / no) --- */
```

### Q2.3

Inside the if statement from Q2.1, you will need to offset the vertex in the direction of the normal to move it outwards in order to create the quad that forms the silhouette outline. This process of changing the location of the vertex is like making a change to the actual 3D geometry of the model, as if you quickly loaded the model into a 3D modeling program, edited the vertex by hand, and resaved the file.  So, we want to make this change while the vertex is still in model space, before transforming it to world space, camera space, and so on.  With this in mind, which version of the vertex normal should you use at this step?  Should you transform the normal as usual by multiplying by the `normalMatrix` in this case?

```
/* --- Write your answer here (yes / no) --- */
```



## License

Material for [CSCI 4611 Spring 2022](https://canvas.umn.edu/courses/290928/assignments/syllabus) by [Evan Suma Rosenberg](https://illusioneering.umn.edu/) is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/).