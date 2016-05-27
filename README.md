# Mobile Console

�ƶ� Web ��չ�����ֻ������ȴһֱû��һ��ԭ���� devTool �����ǿ�����ʹ�á���Ȼ�Ѿ������˺ܶ����������������㷽���������ͻ��������������Ҫ���ٶ�λʱ���ֻ���Ļǰ�����ǲ���Ҳ�Ե������޴룿����ܹ��������� Web ҳ����Ԥ���һ������̨������⣬�ǽ������Ƕ�ϣ��ӵ�е��������졣

<br />

## ��������

![qq 20160527154533](https://cloud.githubusercontent.com/assets/2509085/15601494/3f429aba-2422-11e6-8501-8d3779ffc3ce.png)

<br />

## ��װ

**һ**���� `mobile-console.js` ��ҳ�涥�����á�

```
<script src="mobile-console.js"></script>
```

���� Mobile Console ���û���κ����������Կ��԰��ķ��� jQuery��Zepto �ȵ���������֮ǰ��

<br />

**��**����ʼ��

```javascript
mobileConsole.addPanel([...]) //�ڳ�ʼ��֮ǰ����Զ������
mobileConsole.init()
```

<br />

## ʹ��˵��

Mobile Console ��һ����׵���ҳ���Թ��ߣ�Ĭ�ϰ���������塣

Ĭ����壺
 - **����̨���** ����� id: `console`������ҳ�е� console ����ҳ�еĴ�����Ϣ����ӡ������У�
 - **��Դ���** ����� id: `resource`������ҳ�е� cookie ��httponly�Ķ���������localStorage��sessionStorage ��ӡ������С�

Mobile Console ����������Զ��������������ֵ�������
 
<br />

### ����Զ������

`mobileConsole.addPanel` ��������һ���������飬ÿһ���Ӧһ���Զ���������ݡ����磺

```javascript
//�������
var panelData = {
  id: 'myPanel',
  title: '�ҵ����',
  initFn: function (tabDom, panelDom) {
    panelDom.innerHTML = '����е�����'
  }
}

mobileConsole.addPanel([panelData])
```

###### ���һ���Զ������

<br />

### �������˵��

key | ˵��
---- | ----
id | ���Ψһ��ʾ
title | ������ƣ�����ʾ�� MobileConsole �ı�ǩ����
initFn | MobileConsole **��ʼ��ʱ**��ִ���������� initFn ����������������һ�γ�ʼ������������ 3 ����������Ӧ���ı�ǩ Dom ������� Dom ����������
extend | ������չ������������뷽����

����������ջᱻ MobileConsole ת��Ϊ�����󣬶���ӵ��Ĭ�ϵ������뷽����Ҳ����ͨ�� `extend` ���ݽ�����ӡ�

```javascript
//�������
var panelData = {
  id: 'myPanel',
  title: '�ҵ����',
  initFn: function (tabDom, panelDom) {
    panelDom.innerHTML = '����е�����'
  },
  extend: {
    clear: function () {alert(0)},
    extendData: 100
  }
}

mobileConsole.addPanel([panelData])
```

###### ������ myPanel ����ӵ�� `clear` ������ `extendData` ����

<br />

### �����ر�

Mobile Console �ײ���������ť��һ���������һ���ǹرա�

������ܻ�Ĭ�ϳ��Ե��õ�ǰ������� clear ������������Ĭ����û�и÷����ģ���ͨ�� `extend` ��ӣ�����������ǽ���ǰ�������������

�رհ�ť�Ὣ Mobile Console �رա���ʹ�� `mobileConsole.bone.open()` ���´򿪡�

<br />

### �Ǽܶ���

`mobileConsole.bone` �����ṩ����������

���� | ˵��
---- | ----
open | �� Mobile Console
close | �ر� Mobile Console
getActivePanel | ���ص�ǰ��������

<br />

## Thanks

<br />
 