# dol

1.第一个把迭代次数由三次改成两次，导致变成了2*2个i相乘，结果是四次方

##### 代码如下

 ![QQ截图20161012164129](http://a3.qpic.cn/psb?/4e8c8ef6-8dff-4ace-a581-ed29b1252f80/nmo.dlqFUXy*tfoySFmHjcMej6McEnFQmVRV1gvDDm4!/b/dAoBAAAAAAAA&bo=KQEfACkBHwADACU!&rf=viewer_4)

##### 结果如下

![ep2](http://a3.qpic.cn/psb?/4e8c8ef6-8dff-4ace-a581-ed29b1252f80/TsS3VLNgP0ePjCuvCrHjps9tjOSYIU3keJOg1tq1qBo!/b/dHwBAAAAAAAA&bo=mQX*A5kF*wMDByI!&rf=viewer_4)

##### dot图如下，可见迭代次数变成了两次

 ![dot2](http://a3.qpic.cn/psb?/4e8c8ef6-8dff-4ace-a581-ed29b1252f80/WCYC09yDMXVhu6BY6ZSugv87gWFAtG7Be9jI0ELgyaU!/b/dH8BAAAAAAAA&bo=*wFxAP8BcQADACU!&rf=viewer_4)

2.第二个实验要求把平方改成立方，只需修改square.c,把相乘次数改为3次

    if (p->local->index < p->local->len) {
       DOL_read((void*)PORT_IN, &i, sizeof(float), p);
       i = i*i*i;`
##### 结果如下

![QQ图片20161012163645](http://a1.qpic.cn/psb?/4e8c8ef6-8dff-4ace-a581-ed29b1252f80/CyAXPaVc0F2PDhyMFgF1gQMvbI1cko.AuN0Esgk.H5k!/b/dAsBAAAAAAAA&bo=vgHvAb4B7wEDACU!&rf=viewer_4)

##### dot图如下，这里只修改了函数名没修改类名，尝试过修改，但会报错，应该是遗漏了地方，所以中间的迭代器还叫square

 ![dot](http://a1.qpic.cn/psb?/4e8c8ef6-8dff-4ace-a581-ed29b1252f80/k.*7rfFw.YdYuxuFA*6XNhx23kGd7sgWLASscI7ika4!/b/dAsBAAAAAAAA&bo=*QGvAP0BrwADACU!&rf=viewer_4)

3.感想

这次试验主要目的是让我们理解 dol里面example的原理，了解语言逻辑，题目并不难，但是当我试图修改文件名，就会出现很多错误，要修改很多关联文件，可能还要重新build。还有一点要注意，重跑example前要删除build里面的对应example文件，否则里面文件不会更新，导致dot图错误。