# cpp_opencv

#### 이미지 불러오기

```cpp
int main()
{
	Mat img = imread("01.bmp", IMREAD_COLOR);
	
	imshow("#0", img);

	waitKey(0);
	return 0;
}
```
<br>
#### 이미지를 절반 사이즈로 축소
```cpp
    pyrDown(cv::inputArray src, cv::outputArray dst)
```