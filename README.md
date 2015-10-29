Gulp-2rem
-----

###change the Pixel in your css file into rem .


```js

var gulp     = require('gulp'),
    gulp2rem = require('gulp-2rem');


var option = {
    "root_value": 20,                 // 1rem = 20px
    "unit_precision": 5,              // float length 
    "prop_white_list": [              // the attr you want to change to rem
                "width", 
                "height", 
                "padding",
                "padding-top", 
                "padding-right", 
                "padding-bottom", 
                "padding-left", 
                "margin", 
                "margin-top", 
                "margin-right", 
                "margin-bottom", 
                "margin-left"
    ],
    "replace": false,               //  replace the px value to rem ,or add new attr unit by rem after 
    "media_query": false            //  egg: @media screen and (max-width:320px)
};


gulp.task('px2rem',function(){
    gulp.src('./test/sample/*.css')
        .pipe(gulp2rem(option))
        .pipe(gulp.dest('./test/dest/'));
});

gulp.default(['px2rem'],function(){
    gulp.watch('./test/sample/*.css',['px2rem']);
});
```