#### UIBezierPath弧线

> bezierPathWithArcCenter:radius:startAngle:endAngle:clockwise:

- 该函数有5个参数：

```objective-c
Center: 相当于弧形的中心
radius: 半径
startAngle: 开始的角度
endAngle: 结束的角度
clockwise: 是否是顺时针
```

- 具体的使用方法：

```objective-c
UIBezierPath *rightTopSEPath = 
[UIBezierPath bezierPathWithArcCenter:CGPointMake(self.bounds.size.width, 0)
radius:ppx(150)
startAngle:0
endAngle:kDEGREES(360)
clockwise:NO];
[rightTopSEPath stroke];
```
- 和CAShapeLayer、CABasicAnimation一并使用

```objective-c
CAShapeLayer *unFixedLayer = [CAShapeLayer layer];
unFixedLayer.frame = progressView.bounds;
unFixedLayer.path = path.CGPath;
unFixedLayer.strokeColor = [MakerUntil mk_colorWithHexString:kMainColor].CGColor;
unFixedLayer.fillColor = [UIColor clearColor].CGColor;
unFixedLayer.lineWidth = 5.0f;
[progressView.layer addSublayer:unFixedLayer];

CABasicAnimation *animation = [CABasicAnimation animationWithKeyPath:@"strokeEnd"];
animation.duration = 1.5f;
animation.fromValue = @(0);
animation.toValue = @(1);
animation.removedOnCompletion = NO;
animation.fillMode = kCAFillModeForwards;
animation.timingFunction = [CAMediaTimingFunction functionWithName:kCAMediaTimingFunctionEaseInEaseOut];
[unFixedLayer addAnimation:animation forKey:@""];
    
```
