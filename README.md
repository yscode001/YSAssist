# YSAssist
iOS开发助手，封装常用业务。

建议：使用时，把YSAssist下载下来，拖入工程，进行修改。

## 使用说明：

- Network：基于Alamofire的网络库封装。

~~~swift
// 开始监听网络状态
NetworkManager.shared.startListeningNetworkReachability()
        
// 结束监听网络状态
NetworkManager.shared.stopListeningNetworkReachability()
        
// 请求网络数据
NetworkManager.shared.request(requestObject: NetworkRequestObject(method: .get, route: "", parms: [:]))
~~~

- CurrentUser

	基于Rx对当前用户信息的封装。
~~~swift
// 取值绑定
CurrentUserVM.shared.id.bind(onNext: { [weak self] (userID) in
	print("当前用户ID:\(userID)")
}).dispose()
        
// 保存、更新、退出
CurrentUserVM.shared.save()
CurrentUserVM.shared.update()
CurrentUserVM.shared.logout()
~~~

- Extension

	目前仅包括对字体的封装，如果要修改，直接修改这里。
~~~swift
// 创建字体
let _ = UIFont.ys.create(12, type: .regular)
        
// 设置字体
UILabel().ys.font(12, type: .regular)
UIButton().ys.font(12, type: .regular)
UITextField().ys.font(12, type: .regular)
UITextView().ys.font(12, type: .regular)
~~~
