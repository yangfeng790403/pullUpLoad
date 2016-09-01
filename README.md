# pullUpLoad
/*滑到底部加载数据
 列表内容中的图片要有高度，因为图片不会同步加载过来，否则列表盒子找不到高度
 初始化加载数据后，如果不满一屏且还有数据就再加载数据直到盛满一屏；
 */
 初始化实例：
	var listBox=$(".mCommon_frameContent0_content > div").eq(0);//列表容器
	var pullUp=new mCommon_controlPullUpLoad({ //实例化上拉类
				listOuterBox:listBox,//jquery对象,列表外容器容器，找底边位置用
				loadLineUpY:20,//int型 加载触发线的向上偏移量 ,初始值是列表外容器底边为触发线,如果底部有fixed按钮,这个值就是按钮的高度+10
				loadData:function(){//加载数据回调,有数据执行 this.refresh(true);没有数据执行 this.refresh(false);
				dataLoad(this.refresh,listBox);//数据请求模拟 参数：删除圆球方法，append的容器
				}
			});
