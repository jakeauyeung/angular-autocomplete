基于angularjs的搜索自动补全
===============

指令是修改过来的，修复了很多BUG，支持中文响应

使用方法：

本地数据：
```
<angucomplete id="ex1"
              placeholder="Search countries"
              pause="100"
              selectedobject="selectedCountry"
              localdata="countries"
              searchfields="name"
              titlefield="name"
              minlength="1"
              inputclass="form-control form-control-small"/>
 ```

 API接口数据：
 ```
 <angucomplete id="members"
              placeholder="Search members"
              pause="400"
              selectedobject="testObj"
              url="http://myserver.com/api/user/find?s="
              datafield="results"
              titlefield="firstName,surname"
              descriptionfield="email"
              imagefield="profilePic"
              inputclass="form-control form-control-small"/>
```

### 属性描述
| Attribute        | Description           | Required | Example  |
| :------------- |:-------------| :-----:| :-----|
| id | A unique ID for the field | Yes | members |
| placeholder | Placeholder text for the search field | No | Search members |
| pause | The time to wait (in milliseconds) before searching when the user enters new characters | No | 400 |
| selectedObject | Where to store the selected object in your model/controller (like ng-model) | Yes | myObject |
| url | The remote URL to hit to query for results in JSON. angucomplete will automatically append the search string on the end of this, so it must be a GET request | No | http://myserver.com/api/users/find?searchstr= |
| datafield | The name of the field in the JSON object returned back that holds the Array of objects to be used for the autocomplete list. | No | results |
| titlefield | The name of the field in the JSON objects returned back that should be used for displaying the title in the autocomplete list. Note, if you want to combine fields together, you can comma separate them here (e.g. for a first and last name combined) | Yes | firstName,lastName |
| descriptionfield | The name of the field in the JSON objects returned back that should be used for displaying the description in the autocomplete list | No | twitterUsername |
| imageuri | A http location or directory where images reside | No | http://localhost/images/ |
| imagefield | The name of the field in the JSON objects returned back that should be used for displaying an image in the autocomplete list | No | pic |
| minlength | The minimum length of string required before searching | No | 3 |
| inputclass | The classes to use for styling the input box | No | form-control |
| localdata | The local data variable to use from your controller. Should be an array of objects | No | countriesList |
| searchfields | The fields from your local data to search on (comma separate them) | No | title,description |

![联选](http://jakeauyeung.qiniudn.com/angular-autocomplete.png)
