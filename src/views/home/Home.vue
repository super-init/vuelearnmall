<template>
    <div id="home">
        <navbar class="home-nav">
            <template #left></template>
            <template #center>
                <div class="center">购物街</div>
            </template>
            <template #right></template>
        </navbar>
        <HomeSwiper :banner="banner"/>
        <RecommandViews :recommend="recommend"/>
        <FeatureView/>
        <TabControl :titles="['流行','精款','新选']" class="tab-control"/>
        <GoodsList :goods="goods['pop'].list"/>
        <ul>
            <li>流行1</li>
            <li>流行2</li>
            <li>流行3</li>
            <li>流行4</li>
            <li>流行5</li>
            <li>流行6</li>
            <li>流行7</li>
            <li>流行8</li>
            <li>流行9</li>
            <li>流行10</li>
            <li>流行11</li>
            <li>流行12</li>
            <li>流行13</li>
            <li>流行14</li>
            <li>流行15</li>
            <li>流行16</li>
            <li>流行17</li>
            <li>流行18</li>
            <li>流行19</li>
            <li>流行20</li>
            <li>流行21</li>
            <li>流行22</li>
            <li>流行23</li>
            <li>流行24</li>
            <li>流行25</li>
            <li>流行26</li>
            <li>流行27</li>
            <li>流行28</li>
            <li>流行29</li>
            <li>流行30</li>
            <li>流行31</li>
            <li>流行32</li>
            <li>流行33</li>
            <li>流行34</li>
            <li>流行35</li>
            <li>流行36</li>
            <li>流行37</li>
            <li>流行38</li>
            <li>流行39</li>
            <li>流行40</li>
            <li>流行41</li>
            <li>流行42</li>
            <li>流行43</li>
            <li>流行44</li>
            <li>流行45</li>
            <li>流行46</li>
            <li>流行47</li>
            <li>流行48</li>
            <li>流行49</li>
            <li>流行50</li>
            <li>流行51</li>
            <li>流行52</li>
            <li>流行53</li>
            <li>流行54</li>
            <li>流行55</li>
            <li>流行56</li>
            <li>流行57</li>
            <li>流行58</li>
            <li>流行59</li>
            <li>流行60</li>
            <li>流行61</li>
            <li>流行62</li>
            <li>流行63</li>
            <li>流行64</li>
            <li>流行65</li>
            <li>流行66</li>
            <li>流行67</li>
            <li>流行68</li>
            <li>流行69</li>
            <li>流行70</li>
            <li>流行71</li>
            <li>流行72</li>
            <li>流行73</li>
            <li>流行74</li>
            <li>流行75</li>
            <li>流行76</li>
            <li>流行77</li>
            <li>流行78</li>
            <li>流行79</li>
            <li>流行80</li>
            <li>流行81</li>
            <li>流行82</li>
            <li>流行83</li>
            <li>流行84</li>
            <li>流行85</li>
            <li>流行86</li>
            <li>流行87</li>
            <li>流行88</li>
            <li>流行89</li>
            <li>流行90</li>
            <li>流行91</li>
            <li>流行92</li>
            <li>流行93</li>
            <li>流行94</li>
            <li>流行95</li>
            <li>流行96</li>
            <li>流行97</li>
            <li>流行98</li>
            <li>流行99</li>
            <li>流行100</li>
        </ul>
    </div>
</template>

<script>
    import navbar from "components/common/navbar";
    import HomeSwiper from "./childrenComps/HomeSwiper"
    import RecommandViews from "./childrenComps/RecommandViews";
    import FeatureView from "./childrenComps/FeatureView";
    import TabControl from "../../components/common/tabController/TabControl";
    import GoodsList from "../../components/content/goods/goodsList";
    import {getHomeMultidata,getHomeGoods} from "network/home";

    export default {
        name: "Home",
        components: {
            navbar,
            HomeSwiper,
            RecommandViews,
            FeatureView,
            TabControl,
            GoodsList
        },
        data() {
            return {
                banner: null,
                dKeyword: null,
                keywords: null,
                recommend: null,
                goods:{
                    'pop':{
                        page:0,
                        list:[]
                    },
                    'new':{
                        page:0,
                        list:[]
                    },
                    'sell':{
                        page:0,
                        list:[]
                    }
                }
            }
        },
        created() {
            getHomeMultidata().then(res => {
                this.banner = res.data.banner.list
                this.dKeyword = res.data.dKeyword.list
                this.keywords = res.data.keywords.list
                this.recommend = res.data.recommend.list
            })
            this.getGoods('pop')
            this.getGoods('new')
            this.getGoods('sell')

        },
        methods:{
            getGoods(type){
                let page=this.goods[type].page+1
                getHomeGoods(type,page).then(res=>{
                    // console.log(res);
                    // console.log(res.data.list);
                    this.goods[type].list=this.goods[type].list.concat(res.data.list)
                    console.log(this.goods[type].list);
                    this.goods[type].page++
                })
            }
        }
    }
</script>

<style scoped>
    #home{
        padding-top: 44px;
    }
    .center {
        font-size: 16px;
    }

    .home-nav {
        background-color: var(--color-tint);
        color: #ffffff;
    }
    .tab-control{
        position: sticky;
        top: 44px;
    }

</style>