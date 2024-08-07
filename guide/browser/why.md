---
title: Why Browser Mode? | Browser Mode
outline: deep
---

# 为什么选择浏览器模式?

## 动机

我们开发了 Vitest 浏览器模式功能，以帮助改进测试工作流程并实现更准确、可靠的测试结果。这个实验性的测试 API 增加了在本地浏览器环境中运行测试的功能。在本节中，我们将探讨这个功能背后的动机以及它对测试的好处。

### 不同的测试方式

有不同的方法来测试 JavaScript 代码。一些测试框架在 Node.js 中模拟浏览器环境，而其他框架则在真实浏览器中运行测试。在这种情况下，[jsdom](https://www.npmjs.com/package/jsdom) 是一个模拟浏览器环境的规范实现，可以与 Jest 或 Vitest 等测试运行器一起使用，而其他测试工具，如 [WebdriverIO](https://webdriver.io/) 或 [Cypress](https://www.cypress.io/) 则允许开发者在真实浏览器中测试他们的应用，或者在 [Playwright](https://playwright.dev/) 的情况下提供一个浏览器引擎。


### 模拟警告

在模拟环境（如 jsdom 或 happy-dom）中测试 JavaScript 程序简化了测试设置并提供了易于使用的 API，使它们适用于许多项目并增加了对测试结果的信心。然而，需要牢记的是，这些工具仅模拟浏览器环境而不是实际浏览器，这可能导致模拟环境和真实环境之间存在一些差异。因此，测试结果可能会出现误报或漏报。

为了在测试中获得最高的水平，测试在真实浏览器环境中进行非常重要。这就是为什么我们开发了 Vitest 的浏览器模式功能，允许开发者在浏览器中本地运行测试，并获得更准确、可靠的测试结果。通过浏览器级别的测试，开发者可以更加自信地确保他们的应用在真实场景中能够按照预期工作。

## 缺点

使用 Vitest 浏览器时，重要的是要考虑以下缺点：

### 早期开发

Vitest 的浏览器模式功能仍处于早期开发阶段。因此，它可能尚未完全优化，可能存在一些尚未解决的错误或问题。建议用户使用独立的浏览器端测试运行程序（如 WebdriverIO、Cypress 或 Playwright）来增强 Vitest 浏览器体验。

### 更长的初始化时间

Vitest 浏览器在初始化过程中需要启动提供程序和浏览器，这可能需要一些时间。与其他测试模式相比，这可能导致更长的初始化时间。