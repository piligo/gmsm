# 国密算法库



## 前言

GM SM2/3/4 library based on Golang

基于Go语言的国密SM2/SM3/SM4加密算法库

## 说明

1、改造说明

此库主要是开源库（https://github.com/tjfoc/gmsm）master分支微调改造过来的，主要改造的地方：

```
1、sm2库中关于默认加密未是使用default_uid进行加解密的。对于一些加密处理函数，将nil调整为default_uid
2、x509中关于证书解析时解析为sm2格式的证书
```

2、使用说明：

```
1、此库主要用于https://github.com/piligo/ 中涉及到国密算法相关的项目中使用。
2、fabric国密改造中使用（主要是为了匹配其他语言库例如：java，js等库）
```

## 主要功能


GMSM包含以下主要功能

    SM2: 国密椭圆曲线算法库
        . 支持Generate Key, Sign, Verify基础操作
        . 支持加密和不加密的pem文件格式(加密方法参见RFC5958, 具体实现参加代码)
        . 支持证书的生成，证书的读写(接口兼容rsa和ecdsa的证书)
        . 支持证书链的操作(接口兼容rsa和ecdsa)
        . 支持crypto.Signer接口
    
    SM3: 国密hash算法库
       . 支持基础的sm3Sum操作
       . 支持hash.Hash接口
    
    SM4: 国密分组密码算法库
        . 支持Generate Key, Encrypt, Decrypt基础操作
        . 提供Cipher.Block接口
        . 支持加密和不加密的pem文件格式(加密方法为pem block加密, 具体函数为x509.EncryptPEMBlock)
