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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 'L’applet de connexion de restauration des informations d’identification cc: restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.'
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287082"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="8deaa-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="8deaa-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="8deaa-104">L’applet de connexion de restauration des informations d’identification cc: restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8deaa-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="8deaa-105">Cette cmdlet s’applique à Skype entreprise version Cloud Connector 2,1.</span><span class="sxs-lookup"><span data-stu-id="8deaa-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="8deaa-106">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="8deaa-106">Detailed Description</span></span>

<span data-ttu-id="8deaa-107">L’applet de commande Restore-CcCredentials nettoie toutes les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel de Skype entreprise Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8deaa-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8deaa-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8deaa-108">Parameters</span></span>

<span data-ttu-id="8deaa-109">Aucune</span><span class="sxs-lookup"><span data-stu-id="8deaa-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8deaa-110">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="8deaa-110">Input Types</span></span>

<span data-ttu-id="8deaa-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="8deaa-111">None.</span></span> <span data-ttu-id="8deaa-112">L’applet de commande Restore-CcCredentials n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="8deaa-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8deaa-113">Types de retours</span><span class="sxs-lookup"><span data-stu-id="8deaa-113">Return Types</span></span>

<span data-ttu-id="8deaa-114">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8deaa-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="8deaa-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="8deaa-115">Example</span></span>

<span data-ttu-id="8deaa-116">L’exemple suivant restaure toutes les informations d’identification du déploiement actuel du connecteur Cloud:</span><span class="sxs-lookup"><span data-stu-id="8deaa-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="8deaa-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8deaa-117">See also</span></span>

[<span data-ttu-id="8deaa-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="8deaa-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="8deaa-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="8deaa-119">Set-CcCredential</span></span>](set-cccredential.md)
  

