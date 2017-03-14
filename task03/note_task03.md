### 中间列自适应的三列布局的四种方法
1. `float+margin`

    ```html
    <div class="parent">
        <div class="left">左侧定宽</div>
        <div class="right">右侧定宽</div>
        <div class="center">中间自适应</div>
    </div> 
    ```
    
    ```css
    .parent{
        outline: 1px dotted #099;
    }
    .left,.right{
        width: 100px;
    }
    .left,.right,.center{
        height: 100px;
    }
    .left{
        float: left;
        margin-right: 10px;
        background: #e51400;
    }
    .right{
        float: right;
        margin-left: 10px;
        background: #4eb3b9;
    }
    .center{
        margin-left: 110px;
        margin-right: 110px;
        background: #ff0097;
    }  
    ```
2. `float+overflow`

    ```html
    <div class="parent">
        <div class="left">左侧定宽</div>
        <div class="right">右侧定宽</div>
        <div class="center">中间自适应</div>
    </div> 
    ```
    ```css
    .parent{
        outline: 1px dotted #099;
    }
    .left,.right{
        width: 100px;
    }
    .left,.right,.center{
        height: 100px;
    }
    .left{
        float: left;
        margin-right: 10px;
        background: #e51400;
    }
    .right{
        float: right;
        margin-left: 10px;
        background: #4eb3b9;
    }
    .center{
        overflow: hidden;
        background: #ff0097;
    }
    ```

3. `display:table`

    ```html
    <div class="parent">
        <div class="left"><p>左侧定宽</p></div>
        <div class="center"><p>中间自适应</p></div>
        <div class="right"><p>右侧定宽</p></div>
    </div> 
    ```
    ```css
        p{
            margin: 0;
            padding: 0;
        }
        .parent{
            display: table;
            width: 100%;
            table-layout: fixed;
            outline: 1px dotted #099;
        }
        .left,.center,.right{
            display: table-cell;
        }
        .left p,.right p,.center p{
            height: 100px;
        }
        .left,.right{
            width: 100px;
        }
        .left{
            padding-right: 10px;
        }
        .left p{
            background: #e51400;
        }
        .right{
            padding-left: 10px;
        }
        .right p{
            background: #4eb3b9;
        }
        .center p{
            background: #ff0097;
        }
    ```
    
4. `display:flex`

    ```html
    <div class="parent">
        <div class="left"><p>左侧定宽</p></div>
        <div class="center"><p>中间自适应</p></div>
        <div class="right"><p>右侧定宽</p></div>
    </div> 
    ```
    
    ```css
        p{
            margin: 0;
            padding: 0;
        }
        .parent{
            display: flex;
            outline: 1px dotted #099;
        }
        .left p,.right p,.center p{
            height: 100px;
        }
        .left p{
            background: #e51400;
        }
        .right p{
            background: #4eb3b9;
        }
        .center p{
            background: #ff0097;
        }
        .left,.right{
            width: 100px;
        }
        .left{
            margin-right: 10px;
        }
        .right{
            margin-left: 10px;
        }
        .center{
            flex: 1;
        }
    ```