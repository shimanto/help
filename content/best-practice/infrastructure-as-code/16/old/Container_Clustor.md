# 第15章
## AlibabaCloud Container Clustorについて

&nbsp; 第6章までは Terraformのインストール方法、コード記載方法、実行方法を説明しました。第7章-第18章はユーザ各自でコード作成、応用ができるよう、AlibabaCloudの基本プロダクトサービスの説明を通じて解説します。

* 第7章：AlibabaCloud VPC
* 第8章：AlibabaCloud ECS
* 第9章：AlibabaCloud NW関連（EIP/HTTP/DNS）
* 第10章：AlibabaCloud SLB
* 第11章：AlibabaCloud AutoScale
* 第12章：AlibabaCloud OSS
* 第13章：AlibabaCloud RDS
* 第14章：AlibabaCloud RAM
* **第15章：AlibabaCloud Container Clustor**
* 第16章：AlibabaCloud Kubernetes
* 第17章：AlibabaCloud Kubernetes Managed
* 第18章：AlibabaCloud Container Registry

各章それぞれサンプルを交えて説明します。


<br>
### 15.1 Container Clustor
&nbsp; Terraformのコード構成要素、コードの構成文の書き方です。Terraformの利用ガイドラインに沿って記載してみてください。Terraformのバージョンによっては書き方が異なる場合がありますので、注意が必要です。

```
resource "alicloud_cs_kubernetes" "main" {

  name_prefix           = xxxxx
  availability_zone     = "${data.alicloud_zones.default.zones.0.id}"
  new_nat_gateway       = true
  master_instance_type  = "ecs.n4.small"
  worker_instance_type  = "ecs.n4.small"
  worker_number         = 10
  password              = xxxxxx
  pod_cidr              = xxxxx
  service_cidr          = xxxx
  enable_ssh            = true
  install_cloud_monitor = true
  vswitch_id            = xxxxxx

}
```