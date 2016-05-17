yii2-related-form
===================

It is a widget only for melon.ng to clone form elements of related models.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require tolik505/yii2-related-form
```

or add

```
"tolik505/yii2-related-form": "dev-master"
```

to the require section of your `composer.json` file.

Usage
------------

After CRUD generating add to getFormConfig()
```
[
    'class' => tolik505\relatedForm\RelatedFormWidget::className(),
    'relation' => 'tests', //name of relation
    /*'uploadBehavior' => [ //if needed UploadBehavior
        [
            'attribute' => 'file_id',
            'extensions' => ['png', 'gif', 'jpg', 'jpeg', 'ico', 'svg'],
            'required' => true
        ]
    ],*/
]
```

###Javascript Events

```javascript

$(".dynamicform_wrapper").on("beforeInsert", function(e, item) {
    console.log("beforeInsert");
});

$(".dynamicform_wrapper").on("afterInsert", function(e, item) {
    console.log("afterInsert");
});

$(".dynamicform_wrapper").on("beforeDelete", function(e, item) {
    if (! confirm("Are you sure you want to delete this item?")) {
        return false;
    }
    return true;
});

$(".dynamicform_wrapper").on("afterDelete", function(e) {
    console.log("Deleted item!");
});

$(".dynamicform_wrapper").on("limitReached", function(e, item) {
    alert("Limit reached");
});

```
