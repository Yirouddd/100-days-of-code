# 📘 Lesson [2]: Prompt Iterative

## 📌 Basic Info
- **Date**: 2026-03-02
- **Status**: ✅ Completed

---

## Iterative Process
- Try something  
- Analyze where the result does not give what you want
- Clarify instructions, give more time to think
- Refine prompts with batch of example

---

## Example of problems:
> Problem: 生成的文本太长  
answer：在prompt中添加长度限制  
**note： 语言模型在计算和判断文本长度时依赖于分词器，而分词器在字符统计方面不具备完美的精度。**
  
> Problem：抓错文本细节  
需要训练语言模型根据不同的目标受众不同的方面，输出风格和内容上都适合文本。

## Conclusion
具体来说，第一版Prompt应该满足**明确**和**给模型思考时间**两个原则。
在此基础上，一般的迭代流程是：首先尝试一个初版，分析结果，然后继续该进Prompt，逐步接近最优。
许多成功的Prompt都是通过这种多轮调整得出的。
