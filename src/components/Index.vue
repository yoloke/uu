<template>
  <div>
    <el-carousel :height="computeHeight">
      <el-carousel-item v-for="(item, index) in sliders" :key="index">
        <img :src="item.img" class="slider_img" />
      </el-carousel-item>
    </el-carousel>
    <div class="solve head-label">
      <!-- <div style="text-align: center;" class="font_size_24">
        一站式解决方案
      </div> -->
    </div>
    <!-- 盒子 -->
    <div class="border_parent">
      <el-row :gutter="10">
        <el-col :xs="12" :sm="12" :md="6">
          <div class="border">
            <div class="border_img_parent">
              <img :src="images[1].img" class="img_border" />
            </div>
            <div class="border_title">{{ images[1].title }}</div>
            <div class="border_content_one">{{ images[1].content[0] }}</div>
            <div class="border_content_two">{{ images[1].content[1] }}</div>
          </div>
        </el-col>
        <el-col :xs="12" :sm="12" :md="6">
          <div class="border">
            <div class="border_img_parent">
              <img :src="images[2].img" class="img_border" />
            </div>
            <div class="border_title">{{ images[2].title }}</div>
            <div class="border_content_one">{{ images[2].content[0] }}</div>
            <div class="border_content_two">{{ images[2].content[1] }}</div>
          </div>
        </el-col>
        <el-col :xs="12" :sm="12" :md="6">
          <div class="border">
            <div class="border_img_parent">
              <img :src="images[3].img" class="img_border" />
            </div>
            <div class="border_title">{{ images[3].title }}</div>
            <div class="border_content_one">{{ images[3].content[0] }}</div>
            <div class="border_content_two">{{ images[3].content[1] }}</div>
          </div>
        </el-col>
        <el-col :xs="12" :sm="12" :md="6">
          <div class="border" style="margin-right: 0">
            <div class="border_img_parent">
              <img :src="images[4].img" class="img_border" />
            </div>
            <div class="border_title">{{ images[4].title }}</div>
            <div class="border_content_one">{{ images[4].content[0] }}</div>
            <div class="border_content_two">{{ images[4].content[1] }}</div>
          </div>
        </el-col>
      </el-row>
    </div>
    <!-- 手机端商品展示 -->
    <div id="产品微观" class="head-label">
      <div style="text-align: center;" class="font_size_24">
        产品微观介绍
      </div>
    </div>

    <div class="product_pc" style="display: flex; justify-content: center;">
      <video ref="videoPlayer" controls style="width: 80%; ">
        <source src="../../static/demo.mp4" type="video/mp4" />
      </video>
    </div>
    <!-- 后台管理 -->
    <div class="product_pc" style="display: flex; justify-content: center;">
      <img :src="manages[0].img[0]" class="dd" />
    </div>
    <!-- 产品特点-->
    <div id="产品特点" class="product_spec_title head-label">
      <div style="text-align: center;" class="font_size_24">
        产品特点
      </div>
    </div>
    <div class="product_spec_parent">
      <div class="border_one border_spec">
        <div class="border_spec_inner_one">
          <img :src="spec.product[0].img" style="width: 50px;height: 50px" />
          <div style="margin-left:5px; font-weight: bold;" class="font_size_24">
            {{ spec.product[0].title }}
          </div>
        </div>
        <div style="display: flex;flex-direction: column;">
          <div class="border_spec_content_one">
            {{ spec.product[0].contents[0] }}
          </div>
          <div class="border_spec_inner_last">
            {{ spec.product[0].contents[1] }}
          </div>
        </div>
      </div>
      <div>
        <img :src="computeArrowImg" class="border_spec_img" />
      </div>
      <div class="border_spec">
        <div class="border_spec_inner_one">
          <img :src="spec.product[1].img" style="width: 50px;height: 50px" />
          <div style="margin-left:5px; font-weight: bold;" class="font_size_24">
            {{ spec.product[1].title }}
          </div>
        </div>
        <div style="display: flex;flex-direction: column;">
          <div class="border_spec_content_one">
            {{ spec.product[1].contents[0] }}
          </div>
          <div class="border_spec_inner_last">
            {{ spec.product[1].contents[1] }}
          </div>
        </div>
      </div>
      <div>
        <img :src="computeArrowImg" class="border_spec_img" />
      </div>
      <div class="border_spec">
        <div class="border_spec_inner_one">
          <img :src="spec.product[2].img" style="width: 50px;height: 50px" />
          <div style="margin-left:5px; font-weight: bold;" class="font_size_24">
            {{ spec.product[2].title }}
          </div>
        </div>
        <div style="display: flex;flex-direction: column;">
          <div class="border_spec_content_one">
            {{ spec.product[2].contents[0] }}
          </div>
          <div class="border_spec_inner_last">
            {{ spec.product[2].contents[1] }}
          </div>
        </div>
      </div>
      <div>
        <img :src="computeArrowImg" class="border_spec_img" />
      </div>
      <div class="border_spec" style="margin-right: 0">
        <div class="border_spec_inner_one">
          <img :src="spec.product[3].img" style="width: 50px;height: 50px" />
          <div style="margin-left:5px; font-weight: bold;" class="font_size_24">
            {{ spec.product[3].title }}
          </div>
        </div>
        <div style="display: flex;flex-direction: column;">
          <div class="border_spec_content_one">
            {{ spec.product[3].contents[0] }}
          </div>
          <div class="border_spec_inner_last">
            {{ spec.product[3].contents[1] }}
          </div>
        </div>
      </div>
    </div>
    <!-- 合作伙伴-->
    <div id="合作伙伴" class="cooperation head-label">
      <div style="text-align: center;" class="font_size_24">
        预期合作伙伴
      </div>
    </div>
    <div class="cooperation_parent">
      <div style="margin: 0 20px; text-align: center">
        <img
          style="height: 90px;width: 90px;border-radius: 50%;"
          src="../../static/other/餐饮行业.png"
        />
        <div>餐饮行业</div>
      </div>
      <div style="margin: 0 20px; text-align: center">
        <img
          style="height: 90px;width: 90px;border-radius: 50%;"
          src="../../static/other/船舶运输.png"
        />
        <div>船舶运输</div>
      </div>
      <div style="margin: 0 20px; text-align: center">
        <img
          style="height: 90px;width: 90px;border-radius: 50%;"
          src="../../static/other/原油开采.png"
        />
        <div>原油开采</div>
      </div>
      <div style="margin: 0 20px; text-align: center">
        <img
          style="height: 90px;width: 90px;border-radius: 50%;"
          src="../../static/other/污水处理行业.png"
        />
        <div>污水处理行业</div>
      </div>
    </div>
    <!-- 关于我们-->
    <div id="关于我们" class="about_me head-label">
      <div style="text-align: center;" class="font_size_24">
        关于我们
      </div>
    </div>
    <div style="width: 90%;background-color: #F2F6FC;margin: 10px auto;">
      <div style="display: flex; flex-direction: column;width: 100%;">
        <p class="about_me_p">{{ company[0] }}</p>
        <p class="about_me_p">{{ company[1] }}</p>
        <p class="about_me_p">{{ company[2] }}</p>
        <p class="about_me_p">{{ company[3] }}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Index",
  data() {
    return {
      sliders: [],
      images: [
        {
          img: require("../../static/other/用户管理.png"),
          title: "用户管理",
          content: ["用户消费分析", "用户标签设定"],
        },
        {
          img: require("../../static/other/店铺管理.png"),
          title: "公司管理",
          content: ["公司运营", "公司商品上架"],
        },
        {
          img: require("../../static/other/数据分析.png"),
          title: "数据分析",
          content: ["交易量直观分析", "经营效果智能分析"],
        },
        {
          img: require("../../static/other/用户构建.png"),
          title: "用户互动",
          content: ["营销活动通知", "用户粘连度提升"],
        },
        {
          img: require("../../static/other/品牌渠道.png"),
          title: "品牌渠道",
          content: ["打造公司自主品牌", "品牌多样化管理"],
        },
      ],
      products: [
        {
          img: [
            require("../../static/other/手机端商品.png"),
            require("../../static/other/手机端商品SKU.png"),
          ],
          title: "手机端商品展示 满足多规格显示",
          content: [
            "商品热销分类显示 分类导航显示所有分类",
            "热销商品优先排序 商城首页轮播自定义",
            "商品多规格多价格展示 商品直接在线购买支付",
          ],
        },
      ],
      manages: [
        {
          img: [require("../../static/other/图片1.png")],
          title: "小程序+公众号一体化微信商城管理平台",
          content: [
            "公众号菜单自定义发布 微信图文图片素材管理",
            "商品多规格SKU自定义上架 分类自定义设置",
            "用户管理 用户自定义标签，了解用户消费行为",
            "订单管理 实时掌握商品交易详情",
            "物流闪电发货 实时掌握物流追踪状态",
          ],
        },
      ],
      spec: {
        img: require("../../static/other/arrow.png"),
        product: [
          {
            img: require("../../static/other/手指.png"),
            title: "制备简单，成本低",
            contents: [""],
          },
          {
            img: require("../../static/other/店铺管理.png"),
            title: "废物再利用",
            contents: [""],
          },
          {
            img: require("../../static/other/数据分析.png"),
            title: "耐油污的污染",
            contents: [""],
          },
          {
            img: require("../../static/other/助力零售.png"),
            title: "高效的油水分离性能",
            contents: [""],
          },
        ],
      },
      company: [
        "积极响应国家号召，建设绿色环保家园，为环保事业做出贡献，为油污水处理问题提供更优的解决方案。",
        "对传统膜材料进行改性优化，解决其制备工艺复杂、过滤效率低、成本高等问题。提高废茶渣的利用率，实现环保效益和经济效益的双丰收。",
        "企业精神：以实力为盾，自信为矛。我们坚信成功靠朋友，成长靠对手，成就靠团体。",
      ],
      carousel_height: "550px",
    };
  },
  methods: {},
  mounted() {
    this.sliders = [
      {
        img: require("../../static/slider/a1.jpg"),
      },
      {
        img: require("../../static/slider/a2.jpg"),
      },
      {
        img: require("../../static/slider/a3.jpg"),
      },
      {
        img: require("../../static/slider/a4.jpg"),
      },
    ];
  },
  computed: {
    //计算高度
    computeHeight() {
      let screenHeight = document.body.clientWidth;
      if (screenHeight > 415) {
        return "550px";
      } else {
        return "250px";
      }
    },
    computeArrowImg() {
      let screenHeight = document.body.clientWidth;
      if (screenHeight > 450) {
        return require("../../static/other/arrow.png");
      } else {
        return require("../../static/other/arrow_down.png");
      }
    },
  },
};
</script>

<style scoped>
.border_parent {
  width: 90%;
  margin: auto;
}

.slider_img {
  height: 550px;
  width: 100%;
}

.solve {
  margin-top: 30px;
  margin-bottom: 10px;
}

.border {
  border-radius: 6px;
  border: 1px solid #ebeef5;
  height: auto;
  margin: 10px;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.border_one {
  margin-left: 0;
}

.border_img_parent {
  margin-top: 20px;
  display: flex;
  justify-content: center;
}

.product_mobile_content {
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.product_mobile_img {
  width: 50%;
}

.product_mobile_title {
  font-weight: bold;
  text-align: center;
}

.product_pc_one {
  text-align: center;
  min-height: 400px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.font_size_30 {
  font-size: 1.875em;
}

.product_font_style {
  font-size: 1.125em;
}

.product_pc_img {
  width: 100%;
}
.dd {
  width: 80%;
}

.product_pc_img_div {
  width: 50%;
  float: left;
  display: flex;
  align-items: center;
}

.product_pc {
  display: flex;
  width: 90%;
  margin: 20px auto;
  background: #f2f6fc;
  align-items: center;
}

.product_spec_title {
  margin-top: 30px;
  margin-bottom: 10px;
}

.product_spec_parent {
  display: flex;
  width: 90%;
  margin: 20px auto;
  align-items: center;
  height: auto;
}

.cooperation_parent {
  display: flex;
  justify-content: center;
  width: 90%;
  margin: 20px auto;
  align-items: center;
  height: auto;
}

.border_spec {
  border-radius: 6px;
  border: 1px solid #ebeef5;
  float: left;
  width: 25%;
  height: auto;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.about_me_p {
  font-size: 1.25em;
  font-weight: normal;
  padding: 0 20px;
  margin: 10px;
}

.border_title {
  font-family: "PingFang SC";
  margin-top: 10px;
  font-size: 1.125em;
  font-weight: bold;
  text-align: center;
}

.border_content_one {
  margin-top: 20px;
  font-size: 1.125em;
  text-align: center;
}

.border_content_two {
  margin-top: 5px;
  font-size: 1.125em;
  margin-bottom: 25px;
  text-align: center;
}

.img_border {
  margin-top: 15px;
  width: 80px;
  height: 80px;
}

.border_spec_inner_one {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 35px;
  height: 70px;
}

.border_spec_content_one {
  margin-top: 15px;
  font-size: 1.125em;
  float: left;
  text-align: center;
}

.border_spec_inner_last {
  margin-top: 15px;
  font-size: 1.125em;
  float: left;
  margin-bottom: 25px;
  text-align: center;
}

.cooperation {
  margin-top: 30px;
  width: 100%;
}

.about_me {
  display: flex;
  margin-top: 30px;
  justify-content: center;
  width: 100%;
}

.product_mobile {
  width: 90%;
  align-items: center;
  margin: 20px auto;
  background: #f2f6fc;
}

.product_mobile_img_div {
  width: 50%;
  height: auto;
}

.product_mobile_content_one {
  margin-top: 20px;
  text-align: center;
}

.product_mobile_content_two {
  margin-top: 10px;
  text-align: center;
}

/* 屏幕设备适配 max-device-width: 400px */
@media screen and (max-device-width: 415px) {
  .slider_img {
    height: 250px;
    width: 100%;
  }

  .border_parent {
    display: flex;
    width: 90%;
    margin: auto;
    height: auto;
    flex-direction: column;
  }

  .border {
    border-radius: 6px;
    border: 1px solid #ebeef5;
    float: left;
    width: 100%;
    height: auto;
    margin: 10px 0 auto;
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
    /*background: aquamarine;*/
  }

  .border_img_parent {
    margin-top: 0;
  }

  .product_mobile {
    width: 90%;
    align-items: center;
    margin: 20px auto;
    height: auto;
    background: #f2f6fc;
  }

  .product_mobile_content {
    width: 100%;
    margin-top: 15px;
  }

  .product_mobile_content_one {
    margin-top: 5px;
  }

  .product_mobile_content_two {
    margin-top: 5px;
  }

  .product_mobile_img_div {
    display: flex;
    width: 100%;
    height: auto;
    justify-content: center;
    margin-top: 10px;
    margin-bottom: 15px;
  }

  .product_mobile_img {
    float: left;
  }

  .product_mobile_title {
    font-weight: bold;
  }

  .product_pc_one {
    width: 100%;
    margin-top: 15px;
  }

  .font_size_30 {
    font-size: 1.25em;
  }

  .product_font_style {
    font-size: 1em;
  }

  .product_pc_img {
    height: 280px;
    width: 320px;
  }

  .product_pc_img_div {
    width: 100%;
    float: left;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 15px;
  }

  .product_pc {
    display: flex;
    width: 90%;
    height: auto;
    margin: 20px auto;
    background: #f2f6fc;
    flex-direction: column;
  }

  .head-label {
    display: flex;
    margin-top: 10px;
  }

  .product_spec_parent {
    display: flex;
    width: 90%;
    align-items: center;
    justify-content: center;
    margin: 20px auto;
    height: auto;
    flex-direction: column;
  }

  .border_spec {
    float: left;
    height: auto;
    margin: 8px;
    width: 100%;
    border-radius: 6px;
    border: 1px solid #ebeef5;
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
  }

  .border_title {
    font-family: "PingFang SC";
    margin-top: 5px;
    font-size: 1.125em;
    font-weight: bold;
  }

  .border_content_one {
    margin-top: 5px;
    font-size: 1.125em;
  }

  .border_content_two {
    margin-top: 5px;
    font-size: 1.125em;
    margin-bottom: 8px;
  }

  .img_border {
    margin-top: 8px;
    width: 80px;
    height: 80px;
  }

  .border_spec_inner_one {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 8px;
    /*background-color: aqua;*/
    height: 70px;
  }

  .border_spec_content_one {
    margin-top: 5px;
    font-size: 1.125em;
    float: left;
  }

  .border_spec_inner_last {
    /*background-color: bisque;*/
    margin-top: 5px;
    font-size: 1.125em;
    float: left;
    margin-bottom: 8px;
  }

  .about_me {
    display: flex;
    margin-top: 10px;
    width: 100%;
  }
}

.border_spec_img {
  width: 75px;
  height: 55px;
  align-self: center;
}

.font_size_24 {
  font-size: 1.5em;
}
</style>
