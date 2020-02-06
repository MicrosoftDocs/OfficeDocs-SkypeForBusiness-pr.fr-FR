---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 'L’applet de connexion de restauration des informations d’identification cc : restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.'
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824240"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="12e60-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="12e60-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="12e60-104">L’applet de connexion de restauration des informations d’identification cc : restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="12e60-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="12e60-105">Cette cmdlet s’applique à Skype entreprise version Cloud Connector 2,1.</span><span class="sxs-lookup"><span data-stu-id="12e60-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="12e60-106">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="12e60-106">Detailed Description</span></span>

<span data-ttu-id="12e60-107">L’applet de commande Restore-CcCredentials nettoie toutes les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel de Skype entreprise Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="12e60-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="12e60-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="12e60-108">Parameters</span></span>

<span data-ttu-id="12e60-109">Aucune</span><span class="sxs-lookup"><span data-stu-id="12e60-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="12e60-110">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="12e60-110">Input Types</span></span>

<span data-ttu-id="12e60-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="12e60-111">None.</span></span> <span data-ttu-id="12e60-112">L’applet de commande Restore-CcCredentials n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="12e60-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="12e60-113">Types de retours</span><span class="sxs-lookup"><span data-stu-id="12e60-113">Return Types</span></span>

<span data-ttu-id="12e60-114">Aucun.</span><span class="sxs-lookup"><span data-stu-id="12e60-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="12e60-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="12e60-115">Example</span></span>

<span data-ttu-id="12e60-116">L’exemple suivant restaure toutes les informations d’identification du déploiement actuel du connecteur Cloud :</span><span class="sxs-lookup"><span data-stu-id="12e60-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="12e60-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12e60-117">See also</span></span>

[<span data-ttu-id="12e60-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="12e60-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="12e60-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="12e60-119">Set-CcCredential</span></span>](set-cccredential.md)
  

