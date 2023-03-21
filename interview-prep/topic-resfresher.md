- Software testing, segments of software testing before production
    - Unit Testing - testing individual units/components of the program in isolation
    - Integration Testing - ensure that the individual parts work together
    - System Testing - ensure that the system as a whole works
    - Acceptance Testing - the software is tested in a real-world environment to ensure that it works as expected and meets expectations
- Purpose of testing?
    - https://www.geeksforgeeks.org/types-software-testing/
- Merge 2 or more branches in local environment
    - https://stackoverflow.com/questions/25053697/git-merge-two-local-branches
    - Also, when you try to merge on Github but the merge conflicts are too big/complicated, Git will require you to merge locally and give step by step instructions.
- Microservices?
    - An application that uses microservices is comprised of mini services, as opposed to a monolithic application which we are building.
    - For example, a microservice application for a social media site could have a User microservice, a Post microservice, and an Authentication micro service.
- Decoupling?
    - Decoupling is isolating the code that performs a specific task from the code that performs another task. It’s important because it makes the code more maintainable, reusable, and easier to test
- JDK, JRE, JVM?
    - JDK - 
        - develop and run the Java program
        - Includes development tools and JRE
    - JRE - 
        - run (not develop the program)
        - Contains
            - Deployment technologies
            - User interface toolkits
            - Integration libraries
            - Base Libraries
            - Lang and util libraries
            - JVM
    - JVM
        - Executing the Java program line by line
    - https://www.geeksforgeeks.org/differences-jdk-jre-jvm/
- Heap vs Stack?
    - Heap - 
        - Where all objects live
        - String Pool
    - Stack - 
        - Method invocations and local variables
        - References to objects live here
        - Call stack contains method invocations
        - Stack memory contains primitive values and references to objects
- Data Binding?
    - ReactJS uses one-way data binding
        - Component to View
            - Changes to the component data get reflected in the view
                - Example: using {} to render JS values on the page
        - View to Component
            - Change something in the view would affect the component's data
                - Example: using onChange
- Exceptions
    - Finally Block will execute no matter what happens (excpetion is thrown or not)
- System.err
    - 
- ArrayList vs LinkedList Underlying Representation
    - ArrayList - 
        - underlying structure is an array
        - Because we can't change the size of the array, we need some additional logic for the ArrayList which is dynamically sized and can change
            - If we reach a certain threshold in the array, we make a copy of it and double the size
            - If our array was 3 length and we wanted to add a 4th element, we would create a new array of 6 length and copy everything over
    - LinkedList -
        - Nodes and pointers
        - Think of a train with many train-cars
        - Each train-car has a link/pointer to the next car
        - Head node has a point to the next which has a pointer to the next ...
    - Think about inserting into a LinkedList vs an ArrayList
        - For a LinkedList, we would just have to update the "links" or pointers between the nodes
        - With ArrayList, we would have to make room for the new element by copying every element over by 1 position
- Map Interface
    - Not part of Collections Hierarchy
    - Doesn't have the .iterator method
- char vs varchar:
    - https://www.geeksforgeeks.org/char-vs-varchar-in-sql/