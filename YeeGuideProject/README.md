# YeeGuideProject
### 转载请注明出处

1.本工程在EAFeatureGuideView的基础上,将FeatureGuideView以实例对象的形式,更容易控制对象生命周期。<br>
2.FeatureGuideView现在支持点击屏幕进入下一步操作。

##### 用法
```
FeatureGuideObject *object1 =[[FeatureGuideObject alloc] init];
object1.targetView = m_pRedView ;
object1.introduce =@"介绍开始，新的功能";
object1.buttonTitle =@"知道了";

FeatureGuideObject *object2 =[[FeatureGuideObject alloc] init];
object2.targetView = m_pBlueView ;
object2.introduce =@"介绍开始，新的功能";
object2.introduceFont =[UIFont systemFontOfSize:15];

FeatureGuideObject *object3 =[[FeatureGuideObject alloc] init];
object3.targetView  = m_pGreenView ;
object3.cornerRadius= 25.0f;
object3.introduce =@"介绍开始，新的功能";
object3.buttonTitle =@"知道了";

FeatureGuideObject *object4 =[[FeatureGuideObject alloc] init];
object4.targetViewFrame  = CGRectMake(self.view.frame.size.width-50, self.navigationController.navigationBar.frame.origin.y, 45, 45) ;
object4.introduce =@"介绍开始，新的功能";
object4.cornerRadius =22.5;

[FeatureGuideView showGuideViewWithObjects:@[object4,object1,object2,object3] InView:self.tabBarController.view];

[FeatureGuideView showGuideViewWithObjects:@[object4,object1,object2,object3] version:@"1.0.0" identify:NSStringFromClass([self class]) InView:self.tabBarController.view];


UITableViewCell

//https://www.jianshu.com/p/103d6aac84b4
TableViewCell *cell=[tableView cellForRowAtIndexPath:indexPath];
CGRect targetFramefirst=[cell convertRect:cell.m_pEditBtn.frame toView:tableView];
CGRect targetFrame     =[tableView convertRect:targetFramefirst toView:self.view];
FeatureGuideObject *object1 =[[FeatureGuideObject alloc] init];
object1.targetViewFrame = targetFrame;
object1.introduce =@"介绍开始，新的功能";
object1.buttonTitle =@"知道了";
[FeatureGuideView showGuideViewWithObjects:@[object1] InView:self.tabBarController.view];

```

##### 效果如下
![Simulator Screen Shot - iPhone X - 2018-03-22 at 16.41.15.png](https://upload-images.jianshu.io/upload_images/1488651-ddc43abc5a1f6fcd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)<br>
![Simulator Screen Shot - iPhone X - 2018-03-22 at 16.37.07.png](https://upload-images.jianshu.io/upload_images/1488651-64f82e673b89c4e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 后续添加功能：
1.说明文字支持富文本 <br>
2.特定条件显示控制

##### 借鉴部分
1.[AwesomeIntroGuideView](https://github.com/Bupterambition/AwesomeIntroGuideView)<br>
2.[EAFeatureGuideView](https://github.com/Easence/EAFeatureGuideView)
##### 联系我：13137880636@163.com
