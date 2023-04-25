- [x] Test Mock
- [ ] Iterator Model 迭代器模式
- [x] UML图
- [ ] Sequence Diagrams

# Test Mock
Mock : 模拟

Mocks 是编程到接口非常重要的另一个原因！这句话的意思是，**编程时使用接口可以更容易地创建模拟对象，从而进行单元测试和集成测试。**

举个例子，假设我们正在开发一个电子商务网站，我们需要编写一个购物车模块。购物车模块需要与商品模块进行交互，以便将商品添加到购物车中。为了进行单元测试，我们需要创建一个模拟的商品对象，以便在不依赖于实际商品数据的情况下测试购物车模块。如果我们使用接口来定义商品模块的方法，那么我们可以轻松地创建一个模拟的商品对象，该对象实现了商品接口，并返回预定义的数据。这样，**我们就可以在不依赖于实际商品数据的情况下测试购物车模块，从而提高测试的可靠性和效率。**

因此，编程到接口可以帮助我们更轻松地创建模拟对象，从而进行单元测试和集成测试，提高软件的质量和可维护性。


public interface CreditCardSupplier {
public void charge(int amount);
}
public VisaCreditCard extends CreditCardSupplier { ... }
public TestCreditCard extends CreditCardSupplier { ... }```

#  UML图
[UML](https://blog.csdn.net/m0_37989980/article/details/104470064)

![](assets/Pasted%20image%2020230425173037.png)