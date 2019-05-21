---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  '
ms.openlocfilehash: 59c058f8965bbc6fc011806f383c547c1e7b6cd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286977"
---
# <a name="set-cccredential"></a><span data-ttu-id="5e960-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="5e960-103">Set-CcCredential</span></span>
 
<span data-ttu-id="5e960-104">L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  </span><span class="sxs-lookup"><span data-stu-id="5e960-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="5e960-105">Avec le Cloud Connector version 2,0 et les versions ultérieures, cette applet de contrôle peut également définir les informations de compte de l’administrateur de l’ordinateur virtuel et de l’administrateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="5e960-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="5e960-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="5e960-106">Examples</span></span>
<span data-ttu-id="5e960-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e960-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="5e960-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5e960-108">Example 1</span></span>

<span data-ttu-id="5e960-109">L’exemple suivant spécifie le nom et le mot de passe du compte de l’administrateur de client :</span><span class="sxs-lookup"><span data-stu-id="5e960-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="5e960-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="5e960-110">Detailed Description</span></span>
<span data-ttu-id="5e960-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5e960-111"></span></span>

<span data-ttu-id="5e960-112">L’applet de commande Set-CcCredential définit le nom et le mot de passe du compte de l’administrateur de client.</span><span class="sxs-lookup"><span data-stu-id="5e960-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="5e960-113">Pour les versions antérieures à 2,0, cet administrateur doit être un administrateur général Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e960-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="5e960-114">Le Cloud Connector utilise ce compte pour obtenir les informations de configuration, définir les paramètres de configuration et mettre à jour l’état de l’appareil sur la configuration du client Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e960-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="5e960-115">Avec la version 2,0 et les versions ultérieures, vous pouvez également utiliser cette applet de cmdlet pour mettre à jour les mots de passe des comptes VmAdmin et DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="5e960-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5e960-116">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5e960-116">Parameters</span></span>
<span data-ttu-id="5e960-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5e960-117"></span></span>

|<span data-ttu-id="5e960-118">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="5e960-118">**Parameter**</span></span>|<span data-ttu-id="5e960-119">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="5e960-119">**Required**</span></span>|<span data-ttu-id="5e960-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="5e960-120">**Type**</span></span>|<span data-ttu-id="5e960-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="5e960-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5e960-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="5e960-122">AccountType</span></span> <br/> | <span data-ttu-id="5e960-123">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="5e960-123">Required</span></span> <br/> |<span data-ttu-id="5e960-124">System.String</span><span class="sxs-lookup"><span data-stu-id="5e960-124">System.String</span></span>  <br/> | <span data-ttu-id="5e960-125">La valeur du paramètre doit être «TenantAdmin», «VmAdmin» ou «DomainAdmin».</span><span class="sxs-lookup"><span data-stu-id="5e960-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5e960-126">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="5e960-126">Input Types</span></span>
<span data-ttu-id="5e960-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e960-127"></span></span>

<span data-ttu-id="5e960-p102">Aucun. L’applet de commande Set-CcCredential n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="5e960-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5e960-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="5e960-130">Return Types</span></span>
<span data-ttu-id="5e960-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e960-131"></span></span>

<span data-ttu-id="5e960-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="5e960-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e960-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e960-133">See also</span></span>
<span data-ttu-id="5e960-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e960-134"></span></span>

[<span data-ttu-id="5e960-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="5e960-135">Get-CcCredential</span></span>](get-cccredential.md)
  

