Host_SurfaceMetalGeneration 程序使用说明

1. 参数说明：

XYPIZ：
	说明：XY压电陶瓷的数字信号控制端口

XInitPos：
	说明：X轴起始位置。
	单位：um

XStepLen：
	说明：X轴一步的真实步长。
	单位：um

XStepNum：
	说明：X轴的扫描数量
	单位：列数

YInitPos：
	说明：Y轴起始位置。
	单位：um

YStepLen：
	说明：Y轴一步的真实步长。
	单位：um

YStepNum：
	说明：Y轴的扫描数量
	单位：行数

MonitorLatency：
	说明：电流突变检测时间周期。建议为5~30us。
	单位：us

DescendCycle：
	说明：探针下降过程中，经过几个电流检测周期进行移动。单步总的睡眠时间为MonitorLatency x DescendCycle，建议为5以上。
	单位：个周期

ZDecStepIndex：
	说明：探针下降过程中，单步移动的索引值（目前为0.5nm/index）。
	单位：索引值

ZOffset：
	说明：Z轴的待机位置的索引值
	单位：索引值

DataRequired? :
	说明：是否采集探针每一步的电流、位置和最低位置信息并且存储到Excel中。

OutputVoltIndex：
	说明：探针到达表面之后施加的直流电压索引（0.305185 mV/index）
	触发生命周期：探针到达表面，电流超过基线瞬间开始施加目标电压；探针归位到待机位置切断电压。
	单位：索引值

ThresMultiplier：
	说明：阈值电流——电流相对于待机位置基线电流的倍数，超过之后探针停止下降。默认为2，建议至少为3以上。
	单位：倍数

GradualWithdraw? ：
	说明：探针到达样品表面是否逐步回撤。True为经历StiffLatency后逐步缓慢回撤，False为经历StiffLatency后一次性撤回。

WithdrawLatency：
	说明：探针回撤过程中，单步的睡眠时间。
	单位：us

ZWithdrawStepNum：
	说明：探针回撤步数。达到步数之后，Z方向立马返回待机位置offset。
	单位：步数

StiffLatency：
	说明：Z下降到一定程度，接近表面，电流突破阈值之后，并且在回撤开始之前的硬直时间。
	单位：us


2. 附带的控制FPGA程序名称：FPGA_SurfaceSingleTouch

FPGA资源总使用量：

排线：1586 of 4800

寄存器：2851 of 19200

LUT：3502 of 19200

块内存：12.5KB / 128KB

DSP48s：1 of 32



