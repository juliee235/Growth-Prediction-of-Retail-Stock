# Price-Prediction-of-Retail-Stock
Growth Prediction of Retail Stock Using Financial statement and financial index
โปรเจคนี้มีมีจุดประสงค์เพื่อทำนายเเนวโน้มราคาของหุ้นรายไตรมาสของบริษัทในกลุ่มค้าปลีก(HMPRO,CPALL and etc.)โดยใช้ข้อมูลในงบการเงินเเละดัชนีต่างๆ

## Data
1. Financial statement งบการเงินย้อนหลัง 20 ปีรายไตรมาส
2. Index ดัชนีต่างๆ เช่น GDP,retail index and Consumer Confidence index
   
![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/0f7cc7c9-96bb-4d7c-a26a-f5f28eb6be16)

## Feature engineering
ใช้ความรู้จาก Domain knowledge เทียบตัวเเปลต่างๆในงบการเงินเเบบไตรมาสต่อไตรมาส(QoQ) เเละปีต่อปี(YoY)

## Explore Data Analysis(EDA)
ตั้งคำถาม 3 ข้อ
1. Data มีความเป็น Time series ไหม\
   จากการทดสอบด้วย ADF Test เเละ KPSS Test พบว่า Target มีความ Stationary เเต่เมื่อหา Autocorrelation เเละ Partial Autocorrelation พบว่าที่ Lagtime > 0 ผลของตัวเเปรที่เวลาก่อนหน้าไม่มีผลจ่อเวลาปัจจุบันอย่างมีนัยสำคัญจึงสรุปว่าตัวเเปรไม่มีความเป็น Time series
   ![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/7de69e93-8f4c-4549-b0ed-dfc1902a5e14)

2. ตัวเเปรใดบ้างที่มีความสัมพันธ์กับ Target variable
   พบว่า P/E_qoq, depttoAsset_aoa เเละ Revenue_qoq เป็นตัวเเปลที่มีผลต่อการเเนวโน้มราคาหุ้นในไตรมาสต่อไป
   ![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/62c8d771-4022-42ac-bc25-388939e8628d)

3. Outlier ที่เกิดขึ้นจำนวนมากเกิดจากอะไร
   จากการดูการกระจายตัว(distribution) ของ Target variable พบว่ามี Outlier จำนวนมาก โดยเกิดจาก การปั่นหุ้น เเละข่าวหรือเหตุการต่างๆ
   ![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/f597bac7-f6a1-4c66-a62a-ff912db1a271)
   ![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/852bce91-2d28-4041-bd69-f6f637610500)

#### จากการ EDA พบว่าราคามีความผันผวนมากเเละอ่อนไหวกับข่าวเเละเหตุการณ์ที่อยู่นอกเหนือจากงบการเงิน การทำ Sentiment Analysis จึงเป็นต่วช่วยที่ดี เเต่เนื่องจากระยะเวลาโปรเจ็กต์ที่จำกัด,ข้อมูลตั้งเเต่ปี 2010 ที่หาได้ยาก เเละข่าวเเต่ข่าวสร้าง impact ให้หุ้นเเต่ละตัวไม่เท่ากันถึงเเม้จะเป็นหุ้นค้าปลีกเหมือนกัน
#### Tranform จาก Regression problem to Classification Problem
![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/ca013da3-0334-4b55-b0fe-2dcc1af9f04c)

## Model selection and feature selection
   ![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/4ef64e9c-75e9-406e-8ed8-701b177e3cf9)
   ![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/96da9733-9cdd-4629-a015-72876f21baa1)

## Results
![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/9986607c-e9e2-4284-ac39-53543eba383b)\
Hyperparameter tuning\
![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/fce4ca48-7079-4886-8b16-dd9004690bf2)

## Conclusion
![ภาพ](https://github.com/juliee235/Growth-Prediction-of-Retail-Stock/assets/138569824/9796a523-b894-4217-8a8a-afcbe9a4557b)
