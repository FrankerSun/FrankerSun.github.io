---
layout: post
title: "函数 重构"
category: coding
excerpt: ""
tags: []
image: "/images/refactoring.png"
---


1. Extract Method (提炼方法) -- 常用的重构手法之一  
  动机  
  　　函数过长可能需要注释才能理解代码用途。  
  　　增加代码的清晰度和复用度。  
  做法  
  　　创造一个新函数，以更具函数的意图来命名。（以它“做什么”来命名，而不是“怎样做”）  
  　　即使你想要提炼的代码非常简单，例如只是一条消息或一个函数调用，只要新函数的名称能够以更好地方式昭示代码意图，也应该提炼它，但如果你想不出一个更有意义的名称，就别动。  
  相关  
  　　Split Temporary Variable  
  　　Replace Temp With Query  

2. Inline Method (内联函数)  
　todo