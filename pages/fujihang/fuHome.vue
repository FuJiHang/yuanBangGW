<template>
  <div id="fuHome">
    <!--  -->
    <fuHeader></fuHeader>
    <!--  -->
    <el-carousel>
      <el-carousel-item v-for="(item,index) in banner" :key="index">
        <img :style="{width:width}" :src="item.url" />
      </el-carousel-item>
    </el-carousel>

    <!--  -->
    <div class="news">
      <span class="leftContant">
        <el-tabs v-model="activeName" @tab-click="handleClick">
          <el-tab-pane
            :label="item.name"
            :name="'index'+index"
            v-for="(item,index) in funList"
            :key="index"
          >
            <!--  -->
            <div class="name">元邦明月翡翠首批业主喜迎新居,现已相继办理交房…</div>
            <div
              class="contant"
            >近日，元邦明月翡翠热闹非凡，经过2年多的倾力打造、1年多的精心装修，同时，也在广大业主的翘首企盼中，元邦明月水岸C、D栋商品房盛大交楼，首批业主喜迎新居…</div>
            <div class="time">2020-3-28</div>
            <div class="more">查看更多新闻</div>
          </el-tab-pane>
        </el-tabs>
      </span>
      <img src />
    </div>
  </div>
</template>

<script>
import fuHeader from "../../components/fuHeader";
export default {
  components: {
    fuHeader,
  },
  data() {
    return {
      width: 0,
      banner: [
        {
          url:
            "https://www.yuanbangbjf.com:10443/image/system_icon/banner_01.png",
        },
        {
          url:
            "https://www.yuanbangbjf.com:10443/image/system_icon/banner_02.png",
        },
      ],
      funList: [
        {
          name: "公司动态",
        },
        {
          name: "产业资讯",
        },
        {
          name: "媒体报道",
        },
        {
          name: "社会公益",
        },
      ],
      activeName: "index0",
    };
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    },
  },
  mounted() {
    this.width = window.screen.width + "px";
    console.log(this.width);
  },
};
</script>

<style lang="less">
#fuHome {
  height: 100%;
  background: rgba(255, 246, 236, 1);
  .el-carousel {
    img {
    }
    .el-carousel__container {
      height: 400px;
    }
  }

  //
  .news {
    position: relative;
    margin: 0 auto;
    width: 1200px;
    overflow: hidden;
    display: flex;
    align-items: center;
    background: #fff;
    padding: 34px 74px;
    .leftContant {
      flex: 1;
      .el-tabs__active-bar {
        background: #399b12;
        height: 4px;
      }
      .is-active {
        color: #399b12;
      }
      .el-tabs__nav-wrap::after {
        background: #b0d7a0;
      }
      //
      .el-tab-pane {
        .name {
          color: rgba(63, 101, 208, 1);
          font-size: 20px;
        }
      }
    }
    > img {
      width: 490px;
    }
    .el-tabs__item:hover {
      color: #399b12;
    }
  }
}
</style>