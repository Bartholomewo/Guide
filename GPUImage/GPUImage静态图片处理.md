#### 1.1 GPUImage静态图片处理

- 使用GPUImagePicture处理静态图片。（处理前，处理后）

  <img src="http://oif3pqora.bkt.clouddn.com/Simulator%20Screen%20Shot%202017%E5%B9%B49%E6%9C%881%E6%97%A5%2013.40.30.png" width="320"/><img src="http://oif3pqora.bkt.clouddn.com/Simulator%20Screen%20Shot%202017%E5%B9%B49%E6%9C%881%E6%97%A5%2014.42.34.png" width="320" />

- 代码实现

  ```objective-c
  // 获取到一张需要处理的静态图片
  UIImage *needFilterImage = [UIImage imageNamed:@"face.jpg"];

  // 初始化GPU图片处理器
  GPUImagePicture *imagePicture = [[GPUImagePicture alloc] initWithImage:needFilterImage];

  // 初始化一个褐色底的过滤器
  GPUImageSepiaFilter *filter = [[GPUImageSepiaFilter alloc] init];

  // 把过滤器加入到GPU图片处理器
  [imagePicture addTarget:filter];

  // 开始处理图片
  [filter useNextFrameForImageCapture];
  [imagePicture processImage];

  // 输出处理后的图片
  UIImage *currentFilterImage = [filter imageFromCurrentFramebuffer];

  // 显示图片
  [UIImageView.maker
  .com_setup(self.view)
  .img_image(currentFilterImage)
  .img_end mas_makeConstraints:^(MASConstraintMaker *make) {
      make.edges.equalTo(self.view);
  }];
  ```

  ​