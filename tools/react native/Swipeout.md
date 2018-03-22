

# Swipeout使用

1. 引用
import Swipeout from 'react-native-swipeout';

2. 调用

FlatList 渲染每条记录
```
<FlatList
data={Array}
renderItem={this.renderRow}
keyExtractor={(item, index) => index}/>
```
渲染记录
```
renderRow = (data) => {
        let item = data.item;
        let swipeoutBtns = [{
            backgroundColor: 'red',
            color: 'white',
            text: this.formatMessage('delete'),
            onPress: () => {
                // this.onDelAPI(rowData.text, rowID)
                this.showAsset(item[0]);
            }
        }]
        
        return (
            <Swipeout autoClose={true} right={swipeoutBtns} backgroundColor={color.cardBg}>
                <View style={styles.item} key={item[0]}>
                    <Text style={styles.ItemText}>{item[1]}</Text>
                </View> 
            </Swipeout>
        );
    }
```