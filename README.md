# CountView
```java
**
 * 动画显示数字
 */
public class CountView extends TextView{
    //动画时长 ms
    int duration = 1500;
    float number;
    public CountView(Context context, AttributeSet attrs) {
        super(context, attrs);
    }
    public void showNumberWithAnimation(float number) {
        //修改number属性，会调用setNumber方法
        ObjectAnimator objectAnimator=ObjectAnimator.ofFloat(this,"number",0,number);
        objectAnimator.setDuration(duration);
        //加速器，从慢到快到再到慢
        objectAnimator.setInterpolator(new AccelerateDecelerateInterpolator());
        objectAnimator.start();
    }
    public float getNumber() {
        return number;
    }
    public void setNumber(float number) {
        this.number = number;
        setText(String.format("%1$07.2f",number));
    }
}

```
