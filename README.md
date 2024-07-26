设计一个高级在线购物系统，主要功能包括：
用户注册和登录（包括买家和卖家）
浏览商品（分类、筛选、排序）
添加商品到购物车
下订单（包括订单状态管理）
管理订单（订单跟踪、取消订单）
管理库存
购物车和订单的持久化存储（使用文件或数据库）
折扣和优惠券功能
用户评价和评分系统

1.用户管理
用户类：User（抽象类）
属性：username（用户名）, password（密码）
方法：login()（登录）, logout()（登出）, viewProfile()（查看个人信息）
买家类：Buyer（继承自User）
额外属性：cart（购物车，类型为List<Product>）
额外方法：addToCart(Product product)（添加商品到购物车）, viewCart()（查看购物车）, placeOrder()（下订单）
卖家类：Seller（继承自User）
额外属性：products（商品列表，类型为List<Product>）
额外方法：addProduct(Product product)（添加商品）, viewProducts()（查看自己的商品）
2.商品管理
商品类：Product（具体类）
属性：id（商品ID）, name（商品名）, price（价格）, quantity（库存数量）, category（类别）
方法：构造方法，getter和setter方法，toString()方法用于打印商品信息
商品接口：ProductInterface（接口）
方法：displayDetails()（显示商品详细信息）
商品分类类：ProductCategory（枚举类）
枚举值：ELECTRONICS, CLOTHING, BOOKS, FOOD
3.订单管理
订单类：Order
属性：orderId（订单ID）, products（订单商品列表，类型为List<Product>）, totalAmount（总金额）, status（订单状态，类型为OrderStatus）
方法：构造方法，calculateTotal()（计算订单总金额）, displayOrderDetails()（显示订单详细信息）, updateStatus(OrderStatus status)（更新订单状态）
订单状态类：OrderStatus（枚举类）
枚举值：PENDING, SHIPPED, DELIVERED, CANCELLED
4.折扣和优惠券管理
折扣类：Discount
属性：code（优惠码）, discountPercentage（折扣百分比）
方法：构造方法，getter和setter方法
优惠券类：Coupon
属性：code（优惠码）, discountAmount（优惠金额）
方法：构造方法，getter和setter方法
5.用户评价和评分
评价类：Review
属性：userId（用户ID）, productId（商品ID）, rating（评分）, comment（评论）
方法：构造方法，getter和setter方法