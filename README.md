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
<br>
#### 이진화
```cpp
    threshold(img_gray, img_b, 130, 255, THRESH_BINARY);
```

<br>
#### contours
```cpp
    vector<vector<Point>> contours;
    findContours(img_b, contours, RETR_CCOMP, CHAIN_APPROX_NONE);

    int font = FONT_HERSHEY_COMPLEX;
    double fontScale = 0.8;
    int thickness = 1;
    for (int i = 0; i < contours.size(); i++) {
        if (contourArea(contours[i], false) > 900000) {
            drawContours(img, contours, i, (0, 0, 255), 2);
            cout << contourArea(contours[i], false) << endl;
        }
        ostringstream o_string;
        o_string << to_string(i) << " : " << contourArea(contours[i]);
        //putText(img, o_string.str(), contours[i][0], font, fontScale, Scalar(0, 255, 0), thickness);
    }
```