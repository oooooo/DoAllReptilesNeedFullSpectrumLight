###### tags: `ig`

# 爬蟲的曬燈 (reptileBaskingLight)

整理自 [「如何復制陽光？」](https://hackmd.io/XJjnq3o0TwCgkdRprSr8Eg?view)   
來源影片 [`24:05` 我們需要全光譜光嗎？ `Do we NEED Full Spectrum Light`](https://youtu.be/EhbDx11OMfM?t=2484)

## 太陽的光譜

![一部分的太陽的光譜](https://i.imgur.com/8tHZa4B.png)

**一部分的太陽的光譜 (IR-B 後面切斷)**

- 295nm 以後是 UVB 的部分只有一小點
- 320nm 以後是 UVA
- 400nm 以後進入 "人眼" 可見光部分：紫靛藍綠黃橙紅
- 700nm 以後是紅外線 (Infrared，簡稱 IR) 紅外線還有近中遠的分類[^irabc]，在不同領域分類系統有些微不同

[^irabc]: [不同領域的紅外線 | wikipedia 紅外線](https://zh.m.wikipedia.org/zh-tw/%E7%BA%A2%E5%A4%96%E7%BA%BF) 物體通常會輻射出跨越不同波長的紅外線，但是偵測器的設計通常只能接收感到興趣的特定頻譜寬度以內的輻射。

陽光中有很大部分是紅外線

> #### 自然界的紅外線
>
> 陽光的等效溫度為 5,780k，其熱輻射的頻譜中有一半是紅外線。在海平面上，陽光在的輻照度是 1000W/m2。其中有 527W 的能量是紅外線、445W 是可見光，而 32W 的能量是紫外線。
>
> 「如何復制陽光？」中有說到「The visible light is what heats the animal which is much more than the infrared.」 可見光加熱動物，遠勝紅外線。[^heats]
>
> 當物質吸收電磁波時，就會產生熱，並不一定要吸收紅外線才會產生熱。吸收可見光（約佔 46%）也會產生熱。因為紅外線容易被體表組織所吸收，因此有助於加速血液循環，起消炎鎮痛的功能。紅外線因為屬不可見光，所以即使在缺少可見光的黑暗環境也可產生輻射。

[^heats]: [物理，電磁學，電磁感應](https://highscope.ch.ntu.edu.tw/wordpress/?p=2461)。在陽光中紅外線大約佔 47%，可見光約 46%，紫外線約佔 6%。

目前沒有一款燈可以真正模擬太陽光，所以我們需要混和不同的燈來做到。

## 常見的燈種類：

- 汞蒸氣燈 Mercury-vapor[^mercuryvapor]
- 金屬鹵化物燈 Metal-halide[^metalhalide]
- 螢光燈管 Fluorescent tubes[^fluorescent]
- 白熾燈 Incandescent lamp / 鹵素 halogen[^incandescenthalogen]
- LED[^lightemittingdiode]

### 汞蒸氣燈 Mercury-vapor lamp[^mercuryvapor] 光譜

> - 第一個有 UVB UVA 可見光和紅外線多合一光譜
> - 光譜只有峰值 (汞燈特色)
> - 光色有點綠 導致色偏。對動物影響：動物有不同色覺範圍、影響認知
> - 窄光束
> - 無法調暗、加裝恆溫器
> - 每個燈的輸出品質差異大
>
> ![MegaRay 160w (汞蒸氣燈 mercury vapor) 的光譜](https://i.imgur.com/pAM5W15.png)

[^mercuryvapor]: [汞蒸氣燈 | wikipedia](https://zh.wikipedia.org/wiki/%E6%B0%B4%E9%8A%80%E7%87%88) 發光原理為**氣體放電發光**，是指應用電漿的發光放電效應去產生光。 燈泡內抽去空氣，充入水銀和少量氬氣，通電後水銀蒸發，形成電漿發光。 水銀燈對電壓波動敏感，電壓突然降落就 5% 會造成中途熄滅，待降溫後會重新啟動。又稱：`水銀蒸氣燈 / 水銀燈 / 汞燈`

### 金屬鹵化物燈 (金鹵燈) Metal-halide lamp[^metalhalide] 光譜

> - 逼真的太陽光譜
> - 大量 UVA
> - 被廣泛用於動物生態箱，有很多版本的 UVB 用於爬行動物
> - 設計於照明，紅外線有限
>
> ![Phillips (金屬鹵化物燈 Metal-halide lamp) 的光譜](https://i.imgur.com/HCJj9TE.png)

[^metalhalide]: [金屬鹵化物燈 (金鹵燈) Metal-halide lamp | wikipedia](https://zh.wikipedia.org/wiki/%E9%87%91%E5%B1%AC%E9%B9%B5%E5%8C%96%E7%89%A9%E7%87%88) 發光原理也是**氣體放電發光**。金鹵燈在**水銀蒸氣中加入稀土金屬鹵化物鹽**，加強了亮度，也改善了顏色。

### 螢光燈管 Fluorescent tubes[^fluorescent] 光譜

> - UVB 的部分與太陽光譜非常貼合。
> - 但可見光不連續、不夠亮
>
> ![Arcadia (熒光燈管 fluorescent tubes) 的光譜](https://i.imgur.com/JnDCpZa.png)

[^fluorescent]: [螢光燈管 Fluorescent tubes | wikipedia](https://zh.wikipedia.org/wiki/%E8%9E%A2%E5%85%89%E7%87%88) 發光原理也是**氣體放電發光**。 (水銀燈 + 管壁 "螢光物質" 為螢光燈) 它使用電力在氬或氖氣中激發水銀蒸氣，形成電漿並發出短波紫外線，紫外線被磷光體吸收後，磷光體會發出可見的光以照明，這樣發出可見光的方式屬於**螢光**。螢光管必須設有**安定器**，與**啟動器**配合產生讓氣體發生電離的瞬間高壓。 又稱： `日光燈`

### 白熾燈 Incandescent lamp / 鹵素燈 halogen[^incandescenthalogen] 光譜

> ![白熾燈特徵 incandescent lamp (典型鹵素燈 Typical halogen)](https://i.imgur.com/hyrxqRZ.png)
>
> - 有一點 UVA，隨著**溫度的升高**最後有大量紅外線
> - 熒光燈混和和白熾燈，能很好地補充紅色和紅外線段光譜
> - 添加其他色光來製作自然光線

[^incandescenthalogen]: [白熾燈 Incandescent lamp | wikipedia](https://zh.wikipedia.org/wiki/%E7%99%BD%E7%86%BE%E7%87%88) 發光原理是**熱輻射發光**。加熱到發出可見光的現象稱為 "白熾"。 透過通電，利用電阻把幼細絲線（現代通常為鎢絲）加熱至白熾，用來發光的燈，俗名**鎢絲燈**。「白熾燈泡內注入碘或溴等 "鹵素(惰性)氣體" 的燈稱為**鹵素燈**。高溫下蒸發的鎢絲與鹵素進行化學作用，蒸發的鎢會重新凝固在鎢絲上，形成平衡循環，避免鎢絲過早斷裂；因此鹵素燈比白熾燈更長壽 -- -- [市面上各種光源之燈具探討及解析](https://www.bsmi.gov.tw/wSite/public/Attachment/f1271733163412.pdf)

### LED[^lightemittingdiode] 白色光譜

> - 完全沒有 UVA、 UVB。
> - 偏藍光，藍綠區有個大洞
>
> ![LED 光譜 (Arcadia Jungle Dawn 13W LED nuit)](https://i.imgur.com/6S45eYx.png)

[^lightemittingdiode]: [發光二極體 （light-emitting diode，LED) | wikipedia](https://zh.wikipedia.org/wiki/%E7%99%BC%E5%85%89%E4%BA%8C%E6%A5%B5%E7%AE%A1) 發光原理為**固體電致發光**。是一種半導體光源，當電流通過它時會發光；即一種電致發光的半導體電子元件，其內電子與電子空穴複合，以光子的形式釋放能量。今日能夠發出的光已經遍及可見光、紅外線及紫外線，光度亦提高到相當高的程度。

## 混和不同光譜

### 混和光譜例子 1：

> T5-HO Fluorescent 螢光燈 + metal halide 金屬鹵素燈 + halogen flood 鹵素泛光燈 (類白熾燈)
>
> ![T5-HO Fluorescent 螢光燈 + metal halide 金屬鹵素燈 + halogen flood 鹵素泛光燈 (類白熾燈)](https://i.imgur.com/KsO6tPD.png)
>
> - 很好的 UVB：`T5-HO fluorescent 螢光燈`
> - 大量可見光 `UVA：metal halide 金屬鹵素燈`
> - 累積了紅外線：`halogen flood 鹵素泛光燈`
> - 有填滿光譜

### 混和光譜例子 2：LED 加入混和燈

> 白色 LED (取代白熾燈) + 螢光燈 T5-HO Fluorescent + 鹵素燈 halogen
>
> ![白色 LED (取代白熾燈) + 螢光燈 T5-HO Fluorescent + 鹵素燈 halogen](https://i.imgur.com/geAqXkE.png)
>
> - 很好的 UVB：`T5-HO fluorescent 螢光燈`
> - 大量的紅外線：`halogen 鹵素燈`
> - 但是在藍紫區有個大洞
