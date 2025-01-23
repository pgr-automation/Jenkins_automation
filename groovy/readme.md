# Using Groovy Data Types in Jenkins Pipeline

Groovy data types are essential for handling variables and data structures in Jenkins pipelines. Since Jenkins pipelines are written in Groovy, you can utilize its full range of data types and features.

## Common Groovy Data Types in Jenkins Pipeline

---

### **1. Primitive Data Types**
Groovy supports standard primitive types such as `int`, `float`, `boolean`, `char`, and `double`.

```groovy
pipeline {
    agent any
    stages {
        stage('Primitive Types Example') {
            steps {
                script {
                    int count = 5
                    double percentage = 89.7
                    boolean isSuccessful = true
                    echo "Count: ${count}, Percentage: ${percentage}, Success: ${isSuccessful}"
                }
            }
        }
    }
}
```

---

### **2. String**
Strings in Groovy can be either single-quoted (`'`) or double-quoted (`"`). Double-quoted strings allow interpolation.

```groovy
pipeline {
    agent any
    stages {
        stage('String Example') {
            steps {
                script {
                    String name = "Jenkins"
                    echo "Hello, ${name}!"
                }
            }
        }
    }
}
```

---

### **3. Lists**
Lists are ordered collections of elements and can hold any type of object.

```groovy
pipeline {
    agent any
    stages {
        stage('List Example') {
            steps {
                script {
                    def fruits = ['Apple', 'Banana', 'Cherry']
                    fruits.each { fruit ->
                        echo "Fruit: ${fruit}"
                    }
                }
            }
        }
    }
}
```

---

### **4. Maps**
Maps are key-value pairs and are extremely useful in Jenkins pipelines.

```groovy
pipeline {
    agent any
    stages {
        stage('Map Example') {
            steps {
                script {
                    def person = [name: 'John Doe', age: 30, role: 'DevOps Engineer']
                    echo "Name: ${person.name}, Age: ${person.age}, Role: ${person.role}"
                }
            }
        }
    }
}
```

---

### **5. Ranges**
Ranges represent a sequence of numbers or characters.

```groovy
pipeline {
    agent any
    stages {
        stage('Range Example') {
            steps {
                script {
                    def range = 1..5
                    range.each { number ->
                        echo "Number: ${number}"
                    }
                }
            }
        }
    }
}
```

---

### **6. Closures**
Closures are blocks of code that can be assigned to a variable and executed later.

```groovy
pipeline {
    agent any
    stages {
        stage('Closure Example') {
            steps {
                script {
                    def greet = { name -> echo "Hello, ${name}!" }
                    greet('Jenkins')
                }
            }
        }
    }
}
```

---

### **7. Custom Classes and Objects**
You can define your own classes and create objects in a Jenkins pipeline.

```groovy
pipeline {
    agent any
    stages {
        stage('Class Example') {
            steps {
                script {
                    class Person {
                        String name
                        int age

                        String introduce() {
                            return "My name is ${name} and I am ${age} years old."
                        }
                    }
                    
                    def person = new Person(name: 'Alice', age: 28)
                    echo person.introduce()
                }
            }
        }
    }
}
```

---

## Key Points to Remember:

1. Use the `script` block for Groovy-specific logic inside declarative pipelines.
2. Jenkins pipelines have some restrictions on certain Groovy features for security reasons. If you need to use advanced Groovy features, ensure that the pipeline is approved or running in a trusted environment.
3. Always validate data types and handle exceptions to make your pipeline more robust.

---

Feel free to use these examples as a reference for your Jenkins pipeline scripts!
