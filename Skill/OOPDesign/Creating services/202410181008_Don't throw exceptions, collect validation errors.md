
| id                                                             | hubs    | source                                                     |
| -------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181008_Don't throw exceptions, collect validation errors | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=119]] |
If you want to allow users to correct all their mistakes in one go, before resubmitting the form, you should validate the command’s data before passing the object to the service that’s going to handle it. One way to do this is by adding a validate() method to
the command, which can return a simple list of validation errors. If the list is empty, it means that the submitted data was valid.
![[Pasted image 20241018100952.png]]
Form and validation libraries may offer you more convenient and reusable tools for validation. For instance, the Symfony Form and Validator components work really well with this kind of data transfer object.