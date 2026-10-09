---
layout: docs
title: Modal
label: 模态框
description: 了解如何使用 Bootstrap 模态框，在网站上添加对话框。
group: components
---

模态框是精简但灵活的对话框，只包含必要功能，并带有合理的默认行为。

## 目录

* 目录会替换这里的列表，不含「目录」标题
{:toc}

**按照 HTML5 的语义定义，[HTML 属性 `autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-autofocus) 在 Bootstrap 模态框里不会生效。** 要达到同样效果，请用一段自定义 JavaScript：

{% highlight js %}
$('#myModal').on('shown.bs.modal', function () {
  $('#myInput').focus()
})
{% endhighlight %}

{% callout warning %}
#### 不支持同时打开多个模态框

请不要在另一个模态框还显示时再打开一个。同时显示多个模态框需要自己写代码。
{% endcallout %}

{% callout warning %}
#### 模态框标记的位置

尽量把模态框的 HTML 放在文档的顶层，避免其他组件影响它的外观或功能。
{% endcallout %}

{% callout warning %}
#### 移动设备上的注意点

在移动设备上使用模态框有一些限制。[详见浏览器支持文档]({{ site.baseurl }}/getting-started/browsers-devices/#modals-and-dropdowns-on-mobile)。
{% endcallout %}

### 静态示例

一个已经渲染好的模态框，包含页眉、正文，以及页脚里的一组操作。

<div class="bd-example bd-example-modal">
  <div class="modal">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
            <span aria-hidden="true">&times;</span>
          </button>
          <h4 class="modal-title">模态框标题</h4>
        </div>
        <div class="modal-body">
          <p>这里是正文&hellip;</p>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
          <button type="button" class="btn btn-primary">保存更改</button>
        </div>
      </div><!-- /.modal-content -->
    </div><!-- /.modal-dialog -->
  </div><!-- /.modal -->
</div>

{% highlight html %}
<div class="modal fade">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
          <span aria-hidden="true">&times;</span>
        </button>
        <h4 class="modal-title">模态框标题</h4>
      </div>
      <div class="modal-body">
        <p>这里是正文&hellip;</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
        <button type="button" class="btn btn-primary">保存更改</button>
      </div>
    </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
</div><!-- /.modal -->
{% endhighlight %}

### 在线演示

点击下面的按钮，用 JavaScript 打开模态框。它会从页面顶部滑下并淡入。

<div id="myModal" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">

      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
          <span aria-hidden="true">&times;</span>
        </button>
        <h4 class="modal-title" id="myModalLabel">模态框标题</h4>
      </div>
      <div class="modal-body">
        <h4>模态框中的文字</h4>
        <p>这是一段放在模态框里的说明文字。</p>

        <h4>模态框中的弹出框</h4>
        <p>点击这个<a href="#" role="button" class="btn btn-secondary popover-test" title="标题" data-content="这里是一段示例内容，点击按钮后会显示出来。">按钮</a>会弹出一个弹出框。</p>

        <h4>模态框中的工具提示</h4>
        <p>悬停<a href="#" class="tooltip-test" title="工具提示">这个链接</a>和<a href="#" class="tooltip-test" title="工具提示">那个链接</a>时会显示工具提示。</p>

        <hr>

        <h4>用溢出文字演示滚动</h4>
        <p>这段文字用来把模态框撑高，方便查看内容超出时的滚动效果。</p>
        <p>继续往下是更多占位内容，用来演示模态框内部可以独立滚动。</p>
        <p>当正文比窗口更高时，模态框会在自己的区域里滚动，而不是带动整页。</p>
        <p>这段文字用来把模态框撑高，方便查看内容超出时的滚动效果。</p>
        <p>继续往下是更多占位内容，用来演示模态框内部可以独立滚动。</p>
        <p>当正文比窗口更高时，模态框会在自己的区域里滚动，而不是带动整页。</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
        <button type="button" class="btn btn-primary">保存更改</button>
      </div>

    </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
</div>

<div class="bd-example" style="padding-bottom: 24px;">
  <button type="button" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#myModal">
    打开演示模态框
  </button>
</div>

{% highlight html %}
<!-- 打开模态框的按钮 -->
<button type="button" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#myModal">
  打开演示模态框
</button>

<!-- 模态框 -->
<div class="modal fade" id="myModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
          <span aria-hidden="true">&times;</span>
        </button>
        <h4 class="modal-title" id="myModalLabel">模态框标题</h4>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
        <button type="button" class="btn btn-primary">保存更改</button>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}

{% callout warning %}
#### 让模态框可访问

请给 `.modal` 加上 `role="dialog"` 和指向标题的 `aria-labelledby="..."`，并给 `.modal-dialog` 加上 `role="document"`。

还可以在 `.modal` 上用 `aria-describedby` 为对话框提供说明。
{% endcallout %}

{% callout info %}
#### 嵌入 YouTube 视频

在模态框里嵌入 YouTube 视频时，需要额外的 JavaScript 才能在关闭时自动停止播放。详见这篇 [Stack Overflow 帖子](https://stackoverflow.com/questions/18622508/bootstrap-3-and-youtube-in-modal)。
{% endcallout %}

## 可选尺寸

模态框有两种可选尺寸，把修饰类加在 `.modal-dialog` 上即可。这些尺寸会在特定断点生效，避免窄屏幕出现横向滚动条。

<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-lg">大模态框</button>
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-sm">小模态框</button>
</div>

{% highlight html %}
<!-- 大模态框 -->
<button class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-lg">大模态框</button>

<div class="modal fade bd-example-modal-lg" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      ...
    </div>
  </div>
</div>

<!-- 小模态框 -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-sm">小模态框</button>

<div class="modal fade bd-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-sm">
    <div class="modal-content">
      ...
    </div>
  </div>
</div>
{% endhighlight %}

<div class="modal fade bd-example-modal-lg" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">

      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
          <span aria-hidden="true">&times;</span>
        </button>
        <h4 class="modal-title" id="myLargeModalLabel">大模态框</h4>
      </div>
      <div class="modal-body">
        ...
      </div>
    </div>
  </div>
</div>

<div class="modal fade bd-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-sm">
    <div class="modal-content">

      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
          <span aria-hidden="true">&times;</span>
        </button>
        <h4 class="modal-title" id="mySmallModalLabel">小模态框</h4>
      </div>
      <div class="modal-body">
        ...
      </div>
    </div>
  </div>
</div>

## 去掉动画

如果希望模态框直接出现、而不是淡入，把标记里的 `.fade` 类去掉。

{% highlight html %}
<div class="modal" tabindex="-1" role="dialog" aria-labelledby="..." aria-hidden="true">
  ...
</div>
{% endhighlight %}

## 在模态框里使用栅格

要在模态框里使用 Bootstrap 栅格，把 `.container-fluid` 放进 `.modal-body`，再在这个容器里使用普通的栅格类。

{% example html %}
<div id="gridSystemModal" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="gridModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="关闭"><span aria-hidden="true">&times;</span></button>
        <h4 class="modal-title" id="gridModalLabel">模态框标题</h4>
      </div>
      <div class="modal-body">
        <div class="container-fluid bd-example-row">
          <div class="row">
            <div class="col-md-4">.col-md-4</div>
            <div class="col-md-4 col-md-offset-4">.col-md-4 .col-md-offset-4</div>
          </div>
          <div class="row">
            <div class="col-md-3 col-md-offset-3">.col-md-3 .col-md-offset-3</div>
            <div class="col-md-2 col-md-offset-4">.col-md-2 .col-md-offset-4</div>
          </div>
          <div class="row">
            <div class="col-md-6 col-md-offset-3">.col-md-6 .col-md-offset-3</div>
          </div>
          <div class="row">
            <div class="col-sm-9">
              第 1 层：.col-sm-9
              <div class="row">
                <div class="col-xs-8 col-sm-6">
                  第 2 层：.col-xs-8 .col-sm-6
                </div>
                <div class="col-xs-4 col-sm-6">
                  第 2 层：.col-xs-4 .col-sm-6
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
        <button type="button" class="btn btn-primary">保存更改</button>
      </div>
    </div>
  </div>
</div>
<div class="bd-example bd-example-padded-bottom">
  <button type="button" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#gridSystemModal">
    打开演示模态框
  </button>
</div>
{% endexample %}

## 根据触发按钮改变内容

多个按钮打开同一个模态框，只是内容略有不同？可以用 `event.relatedTarget` 和 [HTML `data-*` 属性](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_data_attributes)（也可以[通过 jQuery](https://api.jquery.com/data/)）按被点击的按钮更换内容。`relatedTarget` 的说明见下方的模态框事件。

{% example html %}
<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@mdo">为 @mdo 打开模态框</button>
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@fat">为 @fat 打开模态框</button>
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@getbootstrap">为 @getbootstrap 打开模态框</button>
  <div class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="关闭">
            <span aria-hidden="true">&times;</span>
          </button>
          <h4 class="modal-title" id="exampleModalLabel">新消息</h4>
        </div>
        <div class="modal-body">
          <form>
            <div class="form-group">
              <label for="recipient-name" class="form-control-label">收件人：</label>
              <input type="text" class="form-control" id="recipient-name">
            </div>
            <div class="form-group">
              <label for="message-text" class="form-control-label">消息：</label>
              <textarea class="form-control" id="message-text"></textarea>
            </div>
          </form>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
          <button type="button" class="btn btn-primary">发送消息</button>
        </div>
      </div>
    </div>
  </div>
</div>
{% endexample %}

{% highlight js %}
$('#exampleModal').on('show.bs.modal', function (event) {
  var button = $(event.relatedTarget) // 触发模态框的按钮
  var recipient = button.data('whatever') // 从 data-* 属性取出信息
  // 如果需要，可以在这里发起 AJAX 请求（并在回调里更新内容）。
  // 更新模态框内容。这里用 jQuery，也可以改用数据绑定或其他方式。
  var modal = $(this)
  modal.find('.modal-title').text('发给 ' + recipient + ' 的新消息')
  modal.find('.modal-body input').val(recipient)
})
{% endhighlight %}

## 高度会变化的模态框

如果模态框在打开后高度发生变化，应调用 `$('#myModal').data('bs.modal').handleUpdate()`，以便在出现滚动条时重新调整位置。

## 用法

模态框插件通过数据属性或 JavaScript 按需显示隐藏内容。它还会给 `<body>` 加上 `.modal-open` 来改变默认滚动，并生成 `.modal-backdrop`，让用户点击模态框外部时可以关闭它。

### 通过数据属性

不用写 JavaScript 也能打开模态框。在按钮这类控制元素上设置 `data-toggle="modal"`，再用 `data-target="#foo"` 或 `href="#foo"` 指定要切换的模态框。

{% highlight html %}
<button type="button" data-toggle="modal" data-target="#myModal">打开模态框</button>
{% endhighlight %}

### 通过 JavaScript

用一行 JavaScript 调用 id 为 `myModal` 的模态框：

{% highlight js %}$('#myModal').modal(options){% endhighlight %}

### 选项

选项可以通过数据属性或 JavaScript 传入。使用数据属性时，把选项名接到 `data-` 后面，例如 `data-backdrop=""`。

<div class="table-responsive">
  <table class="table table-bordered table-striped">
    <thead>
     <tr>
       <th style="width: 100px;">名称</th>
       <th style="width: 50px;">类型</th>
       <th style="width: 50px;">默认值</th>
       <th>说明</th>
     </tr>
    </thead>
    <tbody>
     <tr>
       <td>backdrop</td>
       <td>布尔值，或字符串 <code>'static'</code></td>
       <td>true</td>
       <td>包含遮罩元素。也可以指定 <code>static</code>，这样点击遮罩不会关闭模态框。</td>
     </tr>
     <tr>
       <td>keyboard</td>
       <td>布尔值</td>
       <td>true</td>
       <td>按下 Esc 键时关闭模态框</td>
     </tr>
     <tr>
       <td>focus</td>
       <td>布尔值</td>
       <td>true</td>
       <td>初始化时把焦点放到模态框上。</td>
     </tr>
     <tr>
       <td>show</td>
       <td>布尔值</td>
       <td>true</td>
       <td>初始化时显示模态框。</td>
     </tr>
    </tbody>
  </table>
</div>

### 方法

#### `.modal(options)`

把内容作为模态框激活。可以传入一个可选的选项 `object`。

{% highlight js %}
$('#myModal').modal({
  keyboard: false
})
{% endhighlight %}

#### `.modal('toggle')`

手动切换模态框。**在模态框真正显示或隐藏之前就会返回**（也就是在 `shown.bs.modal` 或 `hidden.bs.modal` 事件发生之前）。

{% highlight js %}$('#myModal').modal('toggle'){% endhighlight %}

#### `.modal('show')`

手动打开模态框。**在模态框真正显示之前就会返回**（也就是在 `shown.bs.modal` 事件发生之前）。

{% highlight js %}$('#myModal').modal('show'){% endhighlight %}

#### `.modal('hide')`

手动隐藏模态框。**在模态框真正隐藏之前就会返回**（也就是在 `hidden.bs.modal` 事件发生之前）。

{% highlight js %}$('#myModal').modal('hide'){% endhighlight %}

### 事件

Bootstrap 的模态框类提供了几个事件，用来接入模态框的行为。所有事件都在模态框自身上触发（也就是 `<div class="modal">`）。

<div class="table-responsive">
  <table class="table table-bordered table-striped">
    <thead>
     <tr>
       <th style="width: 150px;">事件类型</th>
       <th>说明</th>
     </tr>
    </thead>
    <tbody>
     <tr>
       <td>show.bs.modal</td>
       <td>调用 <code>show</code> 实例方法时立即触发。如果由点击引起，被点击的元素可以通过事件的 <code>relatedTarget</code> 属性取得。</td>
     </tr>
     <tr>
       <td>shown.bs.modal</td>
       <td>模态框对用户可见时触发（会等待 CSS 过渡结束）。如果由点击引起，被点击的元素可以通过事件的 <code>relatedTarget</code> 属性取得。</td>
     </tr>
     <tr>
       <td>hide.bs.modal</td>
       <td>调用 <code>hide</code> 实例方法时立即触发。</td>
     </tr>
     <tr>
       <td>hidden.bs.modal</td>
       <td>模态框对用户完全隐藏后触发（会等待 CSS 过渡结束）。</td>
     </tr>
    </tbody>
  </table>
</div>

{% highlight js %}
$('#myModal').on('hidden.bs.modal', function (e) {
  // 在这里处理...
})
{% endhighlight %}
