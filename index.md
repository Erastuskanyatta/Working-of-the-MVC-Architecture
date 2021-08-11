### Introduction
In recent years, the Website has evolved from a static site to a dynamic one with little CSS.

Programmers utilize a variety of patterns and software architectures to make their code easier to understand and develop an application fast.

`Model-View-Controller Architecture (MVC)` is a design pattern for web applications that consists of three interconnected parts(Model View and the Controller).  

MVC frameworks are an essential component of modern web application development. If you happen to walk into any developer's room, don't be amused with the mention of Yii2, Laravel, Django, Ruby any other framework.

### Table of Content
- [What is a Framework?](#what-is-a-framework)
- [Software Architecture Defination](#software-architecture-defination)
- [Model-View-Controller Architecture](#model-view-controller-architecture)
- [How Model View Controller Architecture works](#how-model-view-controller-architecture-works)
- [Benefits of Model-View-Controller ](#benefits-of-model-view-controller )

### What is a Framework?
`Framework` is a skeleton solution(it gives the outline) in which a specific element must be plugged to establish an actual solution. They are made up of a set of related classes that can be specialized to implement an application.

### Software Architecture Definition
Software architecture is the way a system is organized.
This organization covers all components, how they interact with one another, the operating environment, and the software design principles. 

### Model-View-Controller Architecture
Currently, `MVC` is the most top-ranked software architecture that developers are using. It constitutes three interconnected components. These components are: 

1. Model
2. View
3. Controller

These three components have different functions and are built to handle a certain aspect.

#### 1. Model
The model is the data layer of the application. It is responsible for storing and retrieving data from the database and it is also responsible for validating the data.

For example, if you want to create a new user, you will have to create a new user model and then save it to the database.
#### 2. View
The view is the presentation layer of the application. It is used to display the data to the end-user.

For example, if you want to create a user view, you will have to create UI components that the user interacts with such as a login form in an easy-to-understand format.
#### 3. Controller
The controller is the logic layer of the application. It is responsible for processing the user's request and generating the response.

It is used to link the view and the model.

For example, the controller will be responsible for validating the user's input and then it will pass the user's input to the model to save the user.

The diagram below shows how the three components work together and how every component is connected to the other.

![Model-View-Controller Architecture](/visual.png)
### How Model View Controller Architecture works
The browser first sends a request to the controller, the controller then interacts with the model to send and receive data from the database. 

The controller then interacts with the view to generate the response. The view is concerned with displaying the data to the end-user but not with the data itself. It is a dynamic `HTML` file that provides data according to the controller's information

The View is concerned with how the information is presented, not with the end presentation. It will be a dynamic HTML file that renders data based on the information provided by the Controller.

The view then sends its presentation to the controller, the controller then sends the response to the browser which then displays the response to the end-user.


> **Note** Controllers are the glue that binds models, views, and other components together into a runnable application.

This makes programing complex applications easy because the interface and the application logic are separated. 

To understand this concept better, let's take a look at the following example.
<!-- ![MVC Architecture](/engineering-education/How the Model View Controller Architecture Works/visual.png)   -->
Let's have a look at what is happening here. The user first inputs that they want a certain contact record, based on the contact id through the browser.

The browser then sends a request to the controller that it wants a certain contact record. The controller then interacts with the model to get the contact record. The model will find the record from the database and then return it to the controller.

```php
/**
     * Finds the Contact model based on its primary key value.
     * If the model is not found, a 404 HTTP exception will be thrown.
     * @param integer $id
     * @return Contact the loaded model
     * @throws NotFoundHttpException if the model cannot be found
     */
    protected function findModel($id)
    {
        if (($model = Contact::findOne($id)) !== null) {
            return $model;
        }

        throw new NotFoundHttpException('The requested page does not exist.');
    } 
```

The model will then look for the record from the database and then return it to the controller.

```php
/**
     * {@inheritdoc}
     */
    public static function tableName()
    {
        return 'contact';
    }  
```

Once the controller has the record, it will interact with the view to generate the response. The view will then present the record.
### Conclusion
To 


 

<!-- 
    /**
     * Displays a single Contact model.
     * @param integer $id
     * @return mixed
     * @throws NotFoundHttpException if the model cannot be found
     */
    public function actionView($id)
    {
        return $this->render('view', [
            'model' => $this->findModel($id),
        ]);
    } --> 

<!-- 
    <div class="contact-form">

    <?php $form = ActiveForm::begin(); ?>

  <?= $form->field($model, 'contact_id')->textInput() ?> 

    <?= $form->field($model, 'name')->textInput(['maxlength' => true]) ?>

    <?= $form->field($model, 'email')->textInput(['maxlength' => true]) ?>

    <?= $form->field($model, 'subject')->textInput(['maxlength' => true]) ?>

    <?= $form->field($model, 'body')->textInput(['maxlength' => true]) ?>


    <div class="form-group">
        <?= Html::submitButton('app'Save', ['class' => 'btn btn-success']) ?>
    </div>

    <?php ActiveForm::end(); ?>

</div> -->