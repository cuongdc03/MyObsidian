
| id                                   | hubs    | source                                                     |
| ------------------------------------ | ------- | ---------------------------------------------------------- |
| 202410180951_Don't test constructors | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=115]] |
Further down the road, we’ll talk more about exposing data, but for now take the
following advice:
- Only test a constructor for ways in which it should fail.
- Only pass in data as constructor arguments when you need it to implement real
behavior on the object.
- Only add getters to expose internal data when this data is needed by some other client than the test itself.
Once you start adding actual behavior to the object, you will implicitly test the happy path for the constructor anyway, because when doing so you’ll need a fully instantiated object.