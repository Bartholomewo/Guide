#### GPUImage滤镜

- GPUImage3x3ConvolutionFilter

  > 针对图像运行3x3卷积内核
  >
  > 卷积内核：卷积内核是要应用于像素及其8个周围像素的值的3x3矩阵。矩阵以行主顺序指定，左上角的像素为one.one，右下方为three.three。如果矩阵中的值不能加起来为1.0，则图像可能变亮或变暗。

- GPUImageAdaptiveThresholdFilter

  > 确定像素周围的本地亮度，然后将像素转换为低于该亮度的像素，如果高于白色，则将其转换为黑色。这可以用于在不同的照明条件下挑选文本。
  >
  > ```
  > blurRadiusInPixels：用于背景平均模糊半径（以像素为单位）的乘数，默认值为4。
  > ```

- GPUImageAddBlendFilter

  > 通常用于创建两个图像之间的动画变亮模糊效果

- GPUImageAlphaBlendFilter

  > 透明混合,通常用于在背景上应用前景的透明度
  >
  > ```
  > Mix ranges from 0.0 (only image 1) to 1.0 (only image 2), with 1.0 as the normal level
  > mix 属性
  > ```

- GPUImageAmatorkaFilter

  > 基于Amatorka的Photoshop动作的照片过滤器：[http](http://amatorka.deviantart.com/art/Amatorka-Action-2-121069631)://amatorka.deviantart.com/art/Amatorka-Action-2-121069631 。如果要使用此效果，您必须将lookupImamApplication资源文件夹中的lookup_amatorka.png添加到应用程序包中。

- GPUImageAverageLuminanceThresholdFilter

  > 像素色值亮度平均，图像黑白（有类似漫画效果）
  >
  > ```
  > thresholdMultiplier：这是为了达到最终使用阈值而将平均亮度乘以的因素。默认情况下，这是1.0。
  > ```

- GPUImageBilateralFilter

  > 双边模糊
  >
  > ```
  > texelSpacingMultiplier：texel读取间距的乘数，范围从0.0开始，默认值为4.0
  > distanceNormalizationFactor：中心颜色和样本颜色之间的距离的归一化因子，默认值为8.0。
  > ```

- GPUImageBoxBlurFilter

  > 盒状模糊
  >
  > ```
  > texelSpacingMultiplier：纹素之间的间距的乘数，范围从0.0到up，默认值为1.0。调整这可能会稍微增加模糊强度，但会在结果中引入工件。在接触这一个之前先强烈推荐使用其他参数。
  > blurRadiusInPixels：用于模糊的半径（以像素为单位），默认值为2.0。这调整高斯分布函数中的sigma变量。
  > blurRadiusAsFractionOfImageWidth：
  > blurRadiusAsFractionOfImageHeight：设置这些属性将允许模糊半径与图像的大小缩放
  > blurPasses：顺序模糊传入图像的次数。越多越好，过滤器越慢。
  > ```

- GPUImageBrightnessFilter

  > 调整图像的亮度
  >
  > ```
  > brightness：调整亮度（-1.0 - 1.0，默认值为0.0）
  > ```

- GPUImageBulgeDistortionFilter

  > 凸起失真，鱼眼效果
  >
  > ```
  > radius：半径从中心应用失真，默认为0.25
  > center：图像的中心（标准化坐标为0 - 1.0），要扭曲，默认值为（0.5,0.5）
  > scale：要应用的失真量，从-1.0到1.0，默认值为0.5
  > ```

- GPUImageCannyEdgeDetectionFilter

  > 这使用完整的Canny进程来突出显示一个像素宽的边
  >
  > ```
  > texelWidth：
  > texelHeight：这些参数影响检测到的边缘的可见性
  > blurRadiusInPixels：高斯模糊的底层模糊半径。默认值为2.0。
  > blurTexelSpacingMultiplier：底层的模糊纹理间距乘数。默认值为1.0。
  > upperThreshold：任何具有高于该阈值的梯度大小的边将通过并显示在最终结果中。默认值为0.4。
  > lowerThreshold：任何具有低于此阈值的梯度大小的边将失败，并从最终结果中移除。默认值为0.1。
  > ```

- GPUImageCGAColorspaceFilter

  > CGA色彩滤镜，形成黑、浅蓝、紫色块的画面

- GPUImageChromaKeyBlendFilter

  > 用第二个图像选择性地替换第一个图像中的一个颜色
  >
  > ```
  > thresholdSensitivity：要替换的目标颜色需要存在多少颜色匹配（默认值为0.4）
  > smoothing：如何平稳地融合颜色匹配（默认为0.1）
  > ```

- GPUImageChromaKeyFilter

  > 对于图像中的给定颜色，将Alpha通道设置为0.这与GPUImageChromaKeyBlendFilter类似，仅代替在第二个图像中混合匹配的颜色，这不会占用第二个图像，只是将给定的颜色颜色透明。
  >
  > ```
  > thresholdSensitivity：要替换的目标颜色需要存在多少颜色匹配（默认值为0.4）
  > smoothing：如何平稳地融合颜色匹配（默认为0.1）
  > ```

- GPUImageClosingFilter

  > 黑白色调模糊，暗色会被提亮

- GPUImageColorBlendFilter

  > 应用两个图像的颜色混合

- GPUImageColorBurnBlendFilter

  > 色彩加深混合

- GPUImageColorDodgeBlendFilter

  > 色彩减淡混合

- GPUImageColorInvertFilter

  > 反转图像的颜色

- GPUImageColorMatrixFilter

  > 通过对它们应用矩阵来转换图像的颜色
  >
  > ```
  > colorMatrix：用于转换图像中每种颜色的4x4矩阵
  > intensity：新变换颜色取代每个像素的原始颜色的程度
  > ```

- GPUImageColorPackingFilter

  > 色彩丢失，模糊（类似监控摄像效果）

- GPUImageContrastFilter

  > 对比度
  >
  > ```
  > contrast：调整后的对比度（0.0 - 4.0，默认为1.0）
  > ```

- GPUImageCropFilter

  > 将图像**裁剪**到特定区域，然后将该区域仅传递到过滤器的下一个阶段
  >
  > ```
  > cropRegion：裁剪出图像的矩形区域，归一化为0.0 - 1.0的坐标。（0.0，0.0）位置在图像的左上角。
  > ```

- GPUImageCrosshatchFilter

  > 将图像转换为黑白交叉影线图案
  >
  > ```
  > crossHatchSpacing：用作交叉影线间距的图像的小数宽度。默认值为0.03。
  > lineWidth：交叉线的相对宽度。默认值为0.003。
  > ```

- GPUImageDarkenBlendFilter

  > 加深混合,通常用于重叠类型

- GPUImageDifferenceBlendFilter

  > 差异混合,通常用于创建更多变动的颜色

- GPUImageDilationFilter

  > 扩展边缘模糊，变黑白

- GPUImageDissolveBlendFilter

  > 应用两个图像的混合
  >
  > ```
  > mix：第二个图像覆盖第一个图像的程度（0.0 - 1.0，默认值为0.5）
  > ```

- GPUImageDivideBlendFilter

  > 应用两个图像的分割混合

- GPUImageEmbossFilter

  > 浮雕效果，带有点3d的感觉
  >
  > ```
  > intensity: 压花的强度，从0.0到4.0，以1.0为正常水平
  > ```

- GPUImageErosionFilter

  > 侵蚀边缘模糊，变黑白

- GPUImageExclusionBlendFilter

  > 应用两个图像的排除混合

- GPUImageExposureFilter

  > 调整图像的曝光
  >
  > ```
  > exposure：调整曝光（-10.0 - 10.0，默认为0.0）
  > ```

- GPUImageFalseColorFilter

  > 使用图像的亮度在两个用户指定的颜色之间进行混合
  >
  > ```
  > firstColor：第一和第二种颜色分别指定什么颜色代替图像的暗部和亮色区域。默认值为（0.0,0.0,0.5）amd（1.0,0.0,0.0）。
  > secondColor：
  > ```

- GPUImageGammaFilter

  > 伽马线

- GPUImageGaussianBlurFilter

  > 高斯模糊
  >
  > ```
  > texelSpacingMultiplier：纹素之间的间距的乘数，范围从0.0到up，默认值为1.0。调整这可能会稍微增加模糊强度，但会在结果中引入工件。在接触这一个之前先强烈推荐使用其他参数。
  > blurRadiusInPixels：用于模糊的半径（以像素为单位），默认值为2.0。这调整高斯分布函数中的sigma变量。
  > blurRadiusAsFractionOfImageWidth：
  > blurRadiusAsFractionOfImageHeight：设置这些属性将允许模糊半径与图像的大小缩放
  > blurPasses：顺序模糊传入图像的次数。越多越好，过滤器越慢。
  > ```

- GPUImageGaussianBlurPositionFilter

  > **GPUImageGaussianSelectiveBlurFilter**的反方向，只在一个圆圈内应用模糊。
  >
  > ```
  > blurSize：模糊大小的乘数，范围从0.0开始，默认值为1.0
  > blurCenter：模糊中心，默认为0.5，0.5
  > blurRadius：模糊的半径，默认为1.0
  > ```

- GPUImageGaussianSelectiveBlurFilter

  > 保持圆形区域内焦点的高斯模糊
  >
  > ```
  > blurRadiusInPixels：用于模糊的半径（以像素为单位），默认值为5.0。这调整高斯分布函数中的sigma变量。
  > excludeCircleRadius：从模糊中排除的圆形区域的半径
  > excludeCirclePoint：圆形区域的中心被排除在模糊之外
  > excludeBlurSize：模糊部分和清晰圆之间的区域大小
  > aspectRatio：图像的宽高比，用于调整对焦区域的圆度。默认情况下，这与图像宽高比匹配，但您可以覆盖此值。
  > ```

- GPUImageGlassSphereFilter

  > 与**GPUImageSphereRefractionFilter**相同，只有图像不反转，玻璃边缘有一点结霜
  >
  > ```
  > center：应用失真的中心，默认为（0.5,0.5）
  > radius：失真的半径，范围从0.0到1.0，默认值为0.25
  > refractiveIndex：球体折射率，默认值为0.71
  > ```

- GPUImageGrayscaleFilter

  > 灰度

- GPUImageHalftoneFilter

  > 对图像应用半色调效果，如新闻打印
  >
  > ```
  > fractionalWidthOfAPixel：半色调点的大小是图像宽度和高度的一部分（0.0 - 1.0，默认为0.05）
  > ```

- GPUImageHardLightBlendFilter

  > 应用两个图像的硬光混合

- GPUImageHarrisCornerDetectionFilter

  > Harris角点检测，会有绿色小十字显示在图片角点处
  >
  > ```
  > blurRadiusInPixels：底层高斯模糊的半径。默认值为2.0。
  > sensitivity：应用内部缩放因子来调整过滤器中生成的角度图的动态范围。默认值为5.0。
  > threshold：将点检测为角点的阈值。这可能会根据大小，照明条件和iOS设备摄像机类型而有很大差异，因此可能需要一些实验来适应您的情况。默认值为0.20。
  > ```

- GPUImageHazeFilter

  > 朦胧加暗
  >
  > ```
  > distance：施加的颜色的强度。默认值0.-3和.3之间的值最好。
  > slope：颜色变化量。默认值0.-3和.3之间的值最好。
  > ```

- GPUImageHighlightShadowFilter

  > 调整图像的阴影和高光
  >
  > ```
  > shadows：增加减轻阴影，从0.0到1.0，默认值为0.0。
  > highlights：降低亮度，从1.0到0.0，默认值为1.0。
  > ```

- GPUImageHighPassFilter

  > 图像低于某值时显示为黑
  >
  > ```
  > filterStrength：控制先前累积的帧被混合的程度，然后从当前累加帧中减去。范围从0.0到1.0，默认值为0.5。
  > ```

- GPUImageHistogramFilter

  > 它分析输入图像，并创建一个输出直方图，其中出现每个颜色值的频率。该滤镜的输出是3像素高，256像素宽的图像，中心（垂直）像素包含与各种颜色值发生频率对应的像素。每个颜色值占用256个宽度位置中的一个，从左侧的0到右边的255。可以为单个颜色通道（kGPUImageHistogramRed，kGPUImageHistogramGreen，kGPUImageHistogramBlue），图像的亮度（kGPUImageHistogramLuminance）或一次的所有三个颜色通道（kGPUImageHistogramRGB）生成此直方图。
  >
  > ```
  > downsamplingFactor：而不是对每个像素进行采样，这决定了图像的几个部分被采样。默认情况下，这是16，最小为1.这是需要保持饱和直方图，每个颜色值只能在其过载之前记录256个像素.
  > ```

- GPUImageHueBlendFilter

  > 应用两个图像的色调混合

- GPUImageiOSBlurFilter

  > 尝试复制iOS 7上使用的背景模糊，如控制中心。
  >
  > ```
  > blurRadiusInPixels：用于模糊的半径（以像素为单位），默认值为12.0。这调整高斯分布函数中的sigma变量。
  > saturation：饱和度范围从0.0（完全去饱和）到2.0（最大饱和度），0.8作为正常水平
  > downsampling：下采样的程度，然后对输入图像进行上采样，以最小化高斯模糊中的计算，默认值为4.0
  > ```

- GPUImageJFAVoronoiFilter

  > 生成Voronoi映射，用于后期阶段。
  >
  > ```
  > sizeInPixels：各个元素的大小
  > ```

- GPUImageKuwaharaFilter

  > 桑原(Kuwahara)滤波,水粉画的模糊效果；处理时间比较长，慎用
  >
  > ```
  > radius：在整数中指定从中心像素出来的像素数，用于在应用过滤器时进行测试，默认值为4.一个较高的值创建一个更抽象的图像，但是花费更大的处理时间。
  > ```

- GPUImageKuwaharaRadius3Filter

  > 修改版本的Kuwahara过滤器，经过优化，可以工作在三像素半径

- GPUImageLanczosResamplingFilter

  > Lanczos重取样，模糊效果

- GPUImageLevelsFilter

  > 色阶

- GPUImageLightenBlendFilter 

  > 减淡混合,通常用于重叠类型

- GPUImageLocalBinaryPatternFilter

  > 图像黑白化，并有大量噪点

- GPUImageLookupFilter

  > lookup 色彩调整

- GPUImageLowPassFilter

  > 用于图像加亮

- GPUImageLuminosityBlendFilter

  > 应用两个图像的亮度混合

- GPUImageMaskFilter

  > 使用另一个图像来屏蔽一个图像

- GPUImageMedianFilter

  > 取三个颜色分量的中值，超过3x3

- GPUImageMissEtikateFilter

  >  由Etikate小姐基于Photoshop动作的照片过滤器：[http](http://miss-etikate.deviantart.com/art/Photoshop-Action-15-120151961) ://miss-etikate.deviantart.com/art/Photoshop-Action-15-120151961 。如果要使用此效果，则必须将“GPUImage Resources”文件夹中的lookup_miss_etikate.png添加到应用程序包中。

- GPUImageMonochromeFilter

  > 根据每个像素的亮度将图像转换为单色版本
  >
  > ```
  > intensity：特定颜色取代正常图像颜色的程度（0.0 - 1.0，默认值为1.0）
  > color：使用颜色作为效果的基础，以（0.6,0.45,0.3,1.0）为默认值。
  > ```

- GPUImageMosaicFilter

  > 黑白马赛克

- GPUImageMotionBlurFilter

  > 向图像应用定向运动模糊
  >
  > ```
  > blurSize：模糊大小的乘数，范围从0.0开始，默认值为1.0
  > blurAngle：模糊的角度方向，以度为单位。默认为0度
  > ```

- GPUImageMultiplyBlendFilter

  > 应用两个图像的乘法混合

- GPUImageNobleCornerDetectionFilter

  > 在Harris角检测器上运行Noble变体。它的行为如上所述对于Harris检测器。

- GPUImageNonMaximumSuppressionFilter

  > 非最大抑制，只显示亮度最高的像素，其他为黑

- GPUImageNormalBlendFilter

  > 应用两个图像的正常混合

- GPUImageOpacityFilter

  > 不透明度
  >
  > ```
  > opacity：将每个像素的传入Alpha通道乘以（0.0 - 1.0，默认值为1.0）
  > ```

- GPUImageOpeningFilter

  > 黑白色调模糊

- GPUImageOverlayBlendFilter

  > 叠加,通常用于创建阴影效果

- GPUImagePerlinNoiseFilter

  > 柏林噪点，花边噪点
  >
  > ```
  > colorStart：
  > colorFinish：正在生成噪声的颜色范围
  > scale：正在生成噪声的缩放
  > ```

- GPUImagePinchDistortionFilter

  > 收缩失真，凹面镜
  >
  > ```
  > radius：半径从中心应用失真，默认值为1.0
  > center：图像的中心（标准化坐标为0 - 1.0），要扭曲，默认值为（0.5,0.5）
  > scale：要应用的失真量，从-2.0到2.0，默认值为1.0
  > ```

- GPUImagePixellateFilter

  > 像素化
  >
  > ```
  > fractionalWidthOfAPixel：像素的大小是图像宽度和高度的一部分（0.0 - 1.0，默认为0.05）
  > ```

- GPUImagePolarPixellateFilter

  > 同心圆像素化
  >
  > ```
  > center：要应用像素的中心，默认为（0.5，0.5）
  > pixelSize：分数像素大小，分为宽度和高度分量。默认值为（0.05,0.05）
  > ```

- GPUImagePolkaDotFilter

  > 像素圆点花样
  >
  > ```
  > fractionalWidthOfAPixel：点的大小是图像的宽度和高度的一部分（0.0 - 1.0，默认为0.05）
  > dotScaling：每个网格空间占据一个点的几分之一，从0.0到1.0，默认值为0.9。
  > ```

- GPUImagePosterizeFilter

  > 色调分离，形成噪点效果
  >
  > ```
  > colorLevels：减少图像空间的颜色级别数。取值范围为1〜256，缺省值为10。
  > ```

- GPUImagePrewittEdgeDetectionFilter

  > Prewitt边缘检测，边缘以白色突出显示
  >
  > ```
  > texelWidth：
  > texelHeight：这些参数影响检测到的边缘的可见性
  > edgeStrength：调整过滤器的动态范围。更高的值导致更强的边缘，但可以饱和强度的颜色空间。默认值为1.0。
  > ```

- GPUImageRGBClosingFilter

  > 彩色模糊，暗色会被提亮

- GPUImageRGBDilationFilter

  > RGB扩展边缘模糊，有色彩

- GPUImageRGBErosionFilter

  > RGB侵蚀边缘模糊，有色彩

- GPUImageRGBFilter

  > RGB
  >
  > ```
  > 红色：每个颜色通道乘以的归一化值。范围为0.0，默认值为1.0。
  > 绿色：
  > 蓝色：
  > ```

- GPUImageRGBOpeningFilter

  > 彩色模糊

- GPUImageSaturationFilter

  > 饱和度

- GPUImageScreenBlendFilte

  > 屏幕包裹,通常用于创建亮点和镜头眩光

- GPUImageSepiaFilter

  > 褐色（怀旧）

- GPUImageSharpenFilter

  > 锐化

- GPUImageShiTomasiFeatureDetectionFilter

  > ShiTomasi角点检测，与上差别不大

- GPUImageSketchFilter

  > 素描
  >
  > ```
  > texelWidth：
  > texelHeight：这些参数影响检测到的边缘的可见性
  > edgeStrength：调整过滤器的动态范围。更高的值导致更强的边缘，但可以饱和强度的颜色空间。默认值为1.0。
  > ```

- GPUImageSmoothToonFilter

  > 相比上面的效果更细腻，上面是粗旷的画风
  >
  > ```
  > texelWidth：
  > texelHeight：这些参数影响检测到的边缘的可见性
  > blurRadiusInPixels：底层高斯模糊的半径。默认值为2.0。
  > threshold：边缘检测的灵敏度，较低的值更敏感。范围从0.0到1.0，默认值为0.2
  > quantizationLevels：最终图像中要表示的颜色级数。默认值为10.0
  > ```

- GPUImageSobelEdgeDetectionFilter

  > Sobel边缘检测算法(白边，黑内容，有点漫画的反色效果)

- GPUImageSoftEleganceFilter

  > 另一种基于查找的颜色重映射过滤器。如果要使用此效果，您必须将lookup_soft_elegance_1.png和lookup_soft_elegance_2.png从GPUImage Resources文件夹添加到应用程序包中。

- GPUImageSoftLightBlendFilter

  > 柔光混合

- GPUImageSourceOverBlendFilter

  > 源混合

- GPUImageSphereRefractionFilter

  > 球形折射，图形倒立
  >
  > ```
  > center：应用失真的中心，默认为（0.5,0.5）
  > radius：失真的半径，范围从0.0到1.0，默认值为0.25
  > refractiveIndex：球体折射率，默认值为0.71
  > ```

- GPUImageStretchDistortionFilter

  > 伸展失真，哈哈镜
  >
  > ```
  > center：图像的中心（标准化坐标为0 - 1.0），要扭曲，默认值为（0.5,0.5）
  > ```

- GPUImageSubtractBlendFilter

  > 差值混合,通常用于创建两个图像之间的动画变暗模糊效果

- GPUImageSwirlFilter

  > 漩涡，中间形成卷曲的画面
  >
  > ```
  > radius：半径从中心应用失真，默认为0.5
  > center：图像中心（标准化坐标为0 - 1.0），扭曲，默认为（0.5，0.5）
  > angle：要应用于图像的扭曲量，默认值为1.0
  > ```

- GPUImageThresholdSketchFilter

  > 阀值素描，形成有噪点的素

- GPUImageTiltShiftFilter

  > 条纹模糊，中间清晰，上下两端模糊

- GPUImageToneCurveFilter

  > 色调曲线

- GPUImageToonFilter

  > 卡通效果（黑色粗线描边）
  >
  > ```
  > texelWidth：
  > texelHeight：这些参数影响检测到的边缘的可见性
  > 阈值：边缘检测的灵敏度，较低的值更敏感。范围从0.0到1.0，默认值为0.
  > ```

- GPUImageTransformFilter

  > 形状变化
  >
  > ```
  > affineTransform：这需要一个CGAffineTransform来调整2-D中的图像
  > transform3D：这是一个CATransform3D来处理3-D中的图像
  > ignoreAspectRatio：默认情况下，维护变换后的图像的宽高比，但可以将其设置为“是”，使变换与宽高比无关
  > ```

- GPUImageUnsharpMaskFilter

  > 反遮罩锐化

- GPUImageVignetteFilter

  > 晕影，形成黑色圆形边缘，突出中间图像的效果

- GPUImageWhiteBalanceFilter

  > 白平衡

- GPUImageXYDerivativeFilter

  > XYDerivative边缘检测，画面以蓝色为主，绿色为边缘，带彩色

- GPUImageZoomBlurFilter

  > 对图像应用定向运动模糊
  >
  > ```
  > blurSize：模糊大小的乘数，范围从0.0开始，默认值为1.0
  > blurCenter：模糊的归一化中心。（0.5,0.5）
  > ```