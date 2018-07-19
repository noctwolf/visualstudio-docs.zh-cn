---
title: 1x1 视口大小变量 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 168b358bf58dcb2c91814f5460b203873255e275
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433233"
---
# <a name="1x1-viewport-size-variant"></a>1x1 视口大小变量
将所有呈现器目标上的视口尺寸缩小为 1x1 像素。  
  
## <a name="interpretation"></a>解释  
 较小的视口会减少必须阴影的像素数。 但是，较小的视区不会减少的顶点数到具有进程。 将视口尺寸设置为 1x1 像素可有效地消除应用中的像素着色。  
  
 如果此变体显示较大的性能提升，则可能表示你的应用消耗太多填充率。 此外，你的解决方法可为目标平台过高或您的应用程序可能要花费很长时间像素着色来为之后覆盖，也称为*过度绘制*。 较小的帧缓冲区或减少过度绘制量将提高您的应用程序的性能。  
  
## <a name="remarks"></a>备注  
 在每次调用 `ID3D11DeviceContext::OMSetRenderTargets` 或 `ID3D11DeviceContext::RSSetViewports` 之后，视口尺寸将重置为 1x1 像素。  
  
## <a name="example"></a>示例  
 使用以下代码，可重现此变体：  
  
```cpp
D3D11_VIEWPORT viewport;  
viewport.TopLeftX = 0;  
viewport.TopLeftY = 0;  
viewport.Width = 1;  
viewport.Height = 1;  
d3d_context->RSSetViewports(1, &viewport);  
```
