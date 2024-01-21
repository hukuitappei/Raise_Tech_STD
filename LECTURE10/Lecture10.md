# Lecture10課題

Textから以下の通りの課題があり、挑戦。

>CloudFormation を利用して、課題5で作った環境をコード化しましょう。
>コード化ができたら実行してみて、環境が自動で作られることを確認してください。

1. 目的となる環境の確認

   ![ENV](./PICTURE/構成図.png)

2. 必要な要素ごとにCloud Formationを作成する。

   2-1. VPC,RDS,S3,EC2,ALBが必要なので、それぞれ現環境に合わせて作成

       ・Lecture10/Template/VPC.yml
   
       ・Lecture10/Template/RDS.yml
   
       ・Lecture10/Template/S3.yml
   
       ・Lecture10/Template/EC2.yml

       ・Lecture10/Template/ALB.yml
   
   2-2. S3が作成できず、調べたところIAMロールがないとのことでIAMロールを与える部分も作成。
  
       ・Lecture10/Template/IAMROLE.yml

   2-3. 通信に関するセキュリティファイルがばらばらで探しづらかったので一つにまとめた。
 
       ・Lecture10/Template/SECURITY_FILE.yml

3. 作成した状態
以下のように作成に成功しています。

     3-1. Tera Term EC2→RDS
   
   ![ENV](./PICTURE/EC2-RDS接続.PNG)

     3-2. Cloud Formation作成成功
   
   ![ENV](./PICTURE/STACK.PNG)
   
     3-3. TEST-VPCパラメータ

   ![ENV](./PICTURE/TEST-VPC-PARAM.PNG)

     3-4. TEST-RDS

   ![ENV](./PICTURE/TEST-RDS.PNG)

     3-5. TEST-RDSパラメータ

   ![ENV](./PICTURE/TEST-RDS-PARAM.PNG)

     3-6. TEST-S3バケット

   ![ENV](./PICTURE/S3-bucket.PNG)

　　  3-7. TEST-EC2

   ![ENV](./PICTURE/TEST-EC2.PNG)
   
      3-8. TEST-EC2パラメータ

   ![ENV](./PICTURE/TEST-EC2-PARAM.PNG)

   ![ENV](./PICTURE/TEST-SECURITY.PNG)

   ![ENV](./PICTURE/SecurityGroup-ALB.PNG)

   ![ENV](./PICTURE/SecurityGroup-RDS.PNG)

   ![ENV](./PICTURE/SecurityGroup-EC2.PNG)

   ![ENV](./PICTURE/TEST-ROLE.PNG)

   ![ENV](./PICTURE/TEST-ALB.PNG)

 5. 作成して感じたこと
   　各種セキュリティの設定など色々調べながらやったがこれでよいのかわからなかった。
   　S3のName設定がうまくできず、苦労した。
