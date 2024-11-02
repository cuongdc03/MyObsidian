
| id                                            | hubs    | source                                                     |
| --------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181413_Naming runtime exception classes | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=165]] |
For runtime exceptions, a very helpful rule is to finish the sentence, “Sorry,  . . . .” The words at the end will be the name of your exception class. These will be good
names because they communicate how the system tried to perform the requested job,but couldn’t finish it successfully. For example, `CouldNotFindProduct, CouldNot-StoreFile, or CouldNotConnect.`