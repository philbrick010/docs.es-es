---
title: "ICorDebugStepper::StepRange (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72a68000691dd23a55b77265cae839bea8b4ae1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange (Método)
Hace que esta instancia de ICorDebugStepper paso a paso a través de un subproceso que lo contiene y que se devolverán cuando llegue al código situado más allá del último de los intervalos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bStepIn`  
 [in] Establecido en `true` para ir a una función que se llama desde el subproceso. Establecido en `false` para pasar por alto la función.  
  
 `ranges`  
 [in] Una matriz de estructuras COR_DEBUG_STEP_RANGE, cada uno de los cuales especifica un intervalo.  
  
 `cRangeCount`  
 [in] Tamaño de la matriz `ranges`.  
  
## <a name="remarks"></a>Comentarios  
 El `StepRange` método funciona como el [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) método, salvo que no se completa hasta que el código fuera del intervalo especificado se ha alcanzado.  
  
 Esto puede ser más eficaz que la ejecución paso a paso una instrucción a la vez. Los intervalos se especifican como una lista de pares de desplazamiento desde el inicio del marco del paso a paso de desencadene.  
  
 Los intervalos son relativos al código de lenguaje intermedio (MSIL) de Microsoft de un método. Llame a [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) con `false` para hacer que los intervalos relativos al código nativo de un método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]