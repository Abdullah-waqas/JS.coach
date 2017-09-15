# wqs-react-native-collapsible

Animated collapsible component for React Native using ListView.

## Installation
```
npm install --save wqs-react-native-collapsible
```
## Collapsible Component Usage
### Default
<img src="https://image.ibb.co/cVxUGv/Screen_Shot_2017_09_12_at_12_58_10_AM.png" alt="" style="width: 378px;height: 693px;">

```
import Collapsible from 'wqs-react-native-collapsible';
```

```
<Collapsible
  data={jsonData}
  onSelectAll={onSelectAll}
  onSingleSelect={onSingleSelect}
  badgeCountVisible={true}
/>
   ```
### Blue
<img src="https://image.ibb.co/nhM0Oa/Screen_Shot_2017_09_12_at_1_01_55_AM.png" alt="" style="width: 378px;height: 693px;">

```
<Collapsible
  data={jsonData}
  onSelectAll={onSelectAll}
  onSingleSelect={onSingleSelect}
  badgeCountVisible={true}
  checkedImage={'BLUE_CHECK'}
  uncheckedImage={'BLUE_UNCHECK'}
  badgeCountStyle={{backgroundColor: '#55ACEE'}}
/>
```
### Custom Icon & Style
<img src="https://image.ibb.co/i1uy9F/Screen_Shot_2017_09_12_at_1_05_52_AM.png" alt="" style="width: 378px;height: 693px;">

```
<Collapsible
  data={jsonData}
  onSelectAll={onSelectAll}
  onSingleSelect={onSingleSelect}
  badgeCountVisible={true}
  checkedImage={require('./../assets/purple-check.png')}
  uncheckedImage={require('./../assets/purple-uncheck.png')}
  badgeCountStyle={{backgroundColor: '#7F59E0'}}
/>
```

## Properties

#### Data
It is an object array and should be something like  i.e
```
[{
    id:77,
    isAllChecked: false,
    title: 'React-Native',
    children:[{
      id: 11,
      isChecked: false,
      description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. '
    },{
      id: 22,
      isChecked: false,
      description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry.'
    }]
  }
]
```
#### onSelectAll
```
onSelectAll = (updatedData, id) => {
  console.log(updatedData, id);
}

```
- **updatedData**: Wil contain all updated checked/unchecked values.
- **id**: It will show which id is select or deselect.
#### onSingleSelect
```
onSingleSelect = (updatedData, parentId, id) => {
  console.log(updatedData, parentId, id);
}

```
- **updatedData**: Wil contain all updated checked/unchecked values.
- **parentId**: It will return the parent id of selected id i.e in the above example our parent id is 77 if we select checkbox for id 22 or 11.
- **id**: It will show which id is select or deselect.
#### badgeCountVisible
```
badgeCountVisible={true}
OR
badgeCountVisible={false}
```
#### checkedImage
```
checkedImage={require('./../assets/purple-check.png')}
```
#### uncheckedImage
```
uncheckedImage={require('./../assets/purple-uncheck.png')}
```
#### badgeCountStyle
```
badgeCountStyle={{backgroundColor: '#7F59E0'}}
```
#### Sample Code
```
import React from 'react';
import { View } from 'react-native';
import Collapsible from 'wqs-react-native-collapsible';

const App = () => {
  onSelectAll = (updatedData, id) => {
    console.log(updatedData,id);
  }
  onSingleSelect = (updatedData, parentId, selectedId) => {
    console.log(updatedData, parentId, selectedId);
  }
  return (
    <View style={{ flex: 1 }}>
      <Collapsible
        data={jsonData}
        onSelectAll={onSelectAll}
        onSingleSelect={onSingleSelect}
        badgeCountVisible={true}
        checkImage={require('./../assets/purple-check.png')}
        uncheckImage={require('./../assets/purple-uncheck.png')}
        badgeCountStyle={{backgroundColor: '#7F59E0'}}
      />
    </View>
  );
};

export default App;

```
[Github](https://github.com/Abdullah-waqas)
