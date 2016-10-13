# FFBannerView

本Demo使用UICollectionView实现自动无限轮播功能。
主要功能：
1.实现自动轮播，可修改轮播的时间
2.轮播图片可以来自本地，也可来自网络，通过单独的方法进行设置即可。对于加载网络图片时，Demo中使用了YYWebImage，也可自行替换成SDWebImage。
3.重写了和系统UIPageControl一样的功能，可用图片代替PageControl上的点点，也可自定义其颜色以及切换动画。

使用方法：使用方法比较简单。
/**
 *  加载本地图片Banner
 */
- (void)setupLocalBannerImageView
{
    NSArray *array = @[@"1.png", @"2.png", @"3.png", @"4.png", @"5.png"];
    
    FFBannerView *bannerVew = [FFBannerView bannerViewWithFrame:CGRectMake(0, 0, [UIScreen mainScreen].bounds.size.width, 200) locationImageArray:array];
    bannerVew.timeInterval = 2.0;
    [self.view addSubview:bannerVew];
}

/**
 *  加载网络图片Banner
 */
- (void)setupNetWorkBannerImageView
{
    NSArray *array = @[@"http://i3.download.fd.pchome.net/t_960x600/g1/M00/07/09/oYYBAFMv8q2IQHunACi90oB0OHIAABbUQAAXO4AKL3q706.jpg",
                       @"http://images.weiphone.net/attachments/photo/Day_120308/118871_91f6133116504086ed1b82e0eb951.jpg",
                       @"http://benyouhuifile.it168.com/forum/macos/attachments/month_1104/110425215921926a173e0f728e.jpg",
                       @"http://benyouhuifile.it168.com/forum/macos/attachments/month_1104/1104241737046031b3a754f783.jpg"];
    
    FFBannerView *bannerVew = [FFBannerView bannerViewWithFrame:CGRectMake(0, 250, [UIScreen mainScreen].bounds.size.width, 200) netWorkImageArray:array placeHolderImage:nil];
    bannerVew.timeInterval = 2.0;
    bannerVew.pageControlStyle = FFPageControlStyleMiddle;
    bannerVew.delegate = self;
    [self.view addSubview:bannerVew];
}
以上方式即可简单使用，如需自定义PageControl也可继承FFAbstractDotView，做些基本的设置即可。

gitHub下载地址：喜欢的朋友请给个星呗！

欢迎各位一起来讨论，有问题请发邮箱270452746@qq.com或者直接加我QQ：270452746进行讨论。谢谢！
