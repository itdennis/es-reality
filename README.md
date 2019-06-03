[![wercker status](https://app.wercker.com/status/cabf918d05ec2b25ebf6b549f783977a/s/master "wercker status")](https://app.wercker.com/project/byKey/cabf918d05ec2b25ebf6b549f783977a)

# Reality

这是书中事件溯源/CQRS 示例中的事实服务。不同的语言和人群对这类服务可能有不同的名字。此服务提供 CQRS 模式中的查询功能。它的主要职责是处理简单的、为查询而优化的信息获取请求，理想情况下可从缓存读取，或者从已为查询优化的数据获取。

在我们的例子中，*事实*即为所有成员最新报送的当前位置。关于这一服务，很重要的一点的是，它*并不能*体现事件存储中完整的状态。我们无法从中获取到所有位置事件的完整历史记录，而*只能*获取到指定成员，或所有成员的最新位置。

在某些对性能有极限要求的上层架构情形中，也有可能会给事实服务/缓存提供只读服务，或者只写服务。在书中，为了让例子更容易学习，我们并没有对这两种情形加以区分。同时，这种区分经常会导致借助数据库作为集成层，而这则是云原生中的*大忌*。

要注意，虽然将整个数据库作为集层层是一种反模式，但让两个服务使用共享的分布式缓存却是一种推荐的优化方法，它让两个服务都需要处理缓存不命中的情况。换句话说，缓存并不应该作为应用的严格依赖，应用需要能够允许缓存失效和数据丢失的情况。

# Reality API

待续

... 


