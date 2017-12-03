---
title: "ISymUnmanagedDocument::GetSourceLength 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceLength
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b4bf318303b1d787df100051a5c2d3fdd0ac5918
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="7f289-102">ISymUnmanagedDocument::GetSourceLength 方法</span><span class="sxs-lookup"><span data-stu-id="7f289-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="7f289-103">获取嵌入源的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="7f289-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f289-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f289-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f289-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f289-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7f289-106">[out]指向指示嵌入源的长度，以字节为单位的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="7f289-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f289-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7f289-107">Return Value</span></span>  
 <span data-ttu-id="7f289-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7f289-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f289-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f289-109">See Also</span></span>  
 [<span data-ttu-id="7f289-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="7f289-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)