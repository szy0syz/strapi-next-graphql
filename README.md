# strapi-next-graphql

## 🏗️ Setup (part 1)

## 🏠 Restaurants (part 2)

### strapi初始化模型

* 定义 content type
  * 注意选择 desc 字段为text并且支持富文本
* 添加实体
* 授权对应角色访问

### 前端引入GraphQL

* `yarn add react-apollo next-apollo graphql gql recompose`
* 前端lib文件夹创建apollo.js
  * 主要导出withData对象，内存包裹config，填写graphql的请求地址
  * 是个高阶函数，最后要包裹MyApp根节点

### 组件中使用GraphQL的方式

* `import gql from "graphql-tag";`
* `import { graphql } from "react-apollo";`
* 在函数RestaurantList的props取data `data: { loading, error, restaurants`
* 被带有graphql的高阶函数包裹的组件，只要被渲染时就会执行一次请求

```js
const query = gql`
  {
    restaurants {
      id
      name
      description
      image {
        url
      }
    }
  }
`;

export default graphql(query, {
  props: ({ data }) => ({
    data
  })
})(RestaurantList);
```

### react里写style

```js
render() {
    return (
        <div className='search'>search</div>
        <style jsx>
          {`
            .search {
              margin: 20px;
              width: 500px;
            }
          `}
        </style>
    )
}
```

## 🍔 Dishes (part 3)

## 🔐 Authentication (part 4)

## 🛒 Shopping Cart (part 5)

## 💵 Order and Checkout (part 6)

## 🚀 Bonus: Deploy (part 7)