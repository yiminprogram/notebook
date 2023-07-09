# Java Swing

## Frame 視窗

```java
// 建立視窗
JFrame frame = new JFrame();
// 關閉行為
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
// 標題
frame.setTitle("Frame Title");
// 尺寸
frame.setSize(300,300);
// 可見度
frame.setVisible(true);
// icon
ImageIcon icon = new ImageIcon("assets/image.png");
frame.setIconImage(icon.getImage());
// 背景
frame.getContentPane().setBackground(new Color(0xff0000));
frame.getContentPane().setBackground(new Color(255,0,0));
```
