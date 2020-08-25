<template>
  <!--  -->
  <div class="header">
    <span class="logo">
      <img src />
      <span class="name">
        <div class="zh">元邦地产</div>
        <div class="en">YUANBANG PROPERTY</div>
      </span>
    </span>

    <span class="navBar">
      <span
        :class="['li',item.child.length?'isHover':'']"
        v-for="(item,index) in navBar"
        :key="index"
      >
        <span class="to">
          <nuxt-link :to="item.to">{{item.name}}</nuxt-link>
        </span>
        <span class="border"></span>
        <span class="line"></span>
        <span class="list" v-if="item.child.length">
          <span class="child" v-for="(itemc,indexc) in item.child" :key="indexc">
            <nuxt-link :to="item.to">{{itemc.name}}</nuxt-link>
          </span>
        </span>
        <span class="bg" v-if="item.child.length"></span>
      </span>
      <span class="zhen">
        <i class="el-icon-search"></i>
        中/EN
      </span>
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navBar: [
        {
          name: "首页",
          to: "/",
          child: [],
        },
        {
          name: "关于元邦",
          to: "/",
          child: [],
        },
        {
          name: "新闻中心",
          to: "/",
          child: [
            {
              name: "公司动态",
              to: "/",
            },
            {
              name: "产业资讯",
              to: "/",
            },
            {
              name: "媒体报道",
              to: "/",
            },

            {
              name: "社会公益",
              to: "/",
            },
            {
              name: "视频中心",
              to: "/",
            },
            {
              name: "新闻会客室",
              to: "/",
            },
          ],
        },

        {
          name: "元邦产业",
          to: "/",
          child: [],
        },
        {
          name: "投资者关系",
          to: "/",
          child: [],
        },
        {
          name: "商务合作",
          to: "/",
          child: [],
        },
        {
          name: "人力资源",
          to: "/",
          child: [],
        },
      ],
    };
  },
};
</script>

<style lang="less">
//
.header {
  background: rgba(253, 253, 253, 1);
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 1366px;
  margin: 0 auto;
  height: 80px;
  position: relative;

  .logo {
    display: flex;
    align-items: center;
    > img {
      width: 72px;
    }
    .name {
      .zh {
        font-size: 22px;
        font-weight: 800;
      }
      .en {
        font-size: 8px;
      }
    }
  }

  .navBar {
    display: flex;
    align-items: center;
    .border {
      width: 1px;
      height: 20px;
      background: #cccccc;
      display: block;
    }
    .line {
      left: 20%;
      width: 60%;
      height: 5px;
      background: rgba(57, 155, 18, 1);
      position: absolute;
      bottom: 0;
      opacity: 0;
      transition: 0.3s;
    }
    .li {
      font-size: 14px;
      font-weight: 800;
      display: flex;
      align-items: center;
      box-sizing: border-box;
      position: relative;
      height: 80px;
      line-height: 80px;
      .to {
        padding: 0 19px;
      }
      .list {
        width: 800px;
        left: 0;
        top: 73px;
        position: absolute;
        display: none;
        align-items: center;
        z-index: 9;
        .child {
          padding: 0 19px;
          a {
            color: rgb(255, 255, 255);
            transition: .3s;
          }
        }
        .child:hover a {
          color: #399b12;
        }
      }
    }
    .li:hover {
      .line {
        opacity: 1;
      }
    }
    .bg {
      position: absolute;
      left: -1800px;
      top: 80px;
      width: 4000px;
      height: 0;
      background: rgba(0, 0, 0, 1);
      opacity: 0.49;
      transition: 0.2s;
      z-index: 8;
    }
    .isHover:hover {
      .bg {
        height: 62px;
      }
      .list {
        display: flex;
        .child {
          animation: sss 0.4s;
        }
      }
    }
    .zhen {
      padding: 0 25px;
      font-size: 14px;
      font-weight: 800;
      display: flex;
      align-items: center;
    }
    .el-icon-search {
      font-weight: 800;
      margin-right: 10px;
      font-size: 18px;
    }
  }
}
@keyframes sss {
  0% {
    opacity: 0;
    transform: translateX(80px);
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>