---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  '
ms.openlocfilehash: 547f0b87b006347a337a2c25222aecbd4f402669
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876640"
---
# <a name="set-cccredential"></a><span data-ttu-id="8acbd-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="8acbd-103">Set-CcCredential</span></span>
 
<span data-ttu-id="8acbd-104">L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  </span><span class="sxs-lookup"><span data-stu-id="8acbd-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="8acbd-105">Avec le nuage connecteur version 2.0 et versions ultérieure, cette applet de commande peut également définir les informations de compte de l’administrateur de l’ordinateur virtuel et de l’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="8acbd-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="8acbd-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="8acbd-106">Examples</span></span>
<span data-ttu-id="8acbd-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8acbd-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="8acbd-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8acbd-108">Example 1</span></span>

<span data-ttu-id="8acbd-109">L’exemple suivant spécifie le nom et le mot de passe du compte de l’administrateur de client :</span><span class="sxs-lookup"><span data-stu-id="8acbd-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="8acbd-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="8acbd-110">Detailed Description</span></span>
<span data-ttu-id="8acbd-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8acbd-111"></span></span>

<span data-ttu-id="8acbd-112">L’applet de commande Set-CcCredential définit le nom et le mot de passe du compte de l’administrateur de client.</span><span class="sxs-lookup"><span data-stu-id="8acbd-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="8acbd-113">Pour les versions antérieures à 2.0, cet administrateur doit être un administrateur Global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8acbd-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="8acbd-114">Nuage connecteur utilise ce compte pour obtenir des informations de configuration, définissez les paramètres de configuration et d’état d’application de mise à jour pour la configuration du client Office 365.</span><span class="sxs-lookup"><span data-stu-id="8acbd-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="8acbd-115">Avec la version 2.0 et versions ultérieures, vous pouvez utiliser également cette applet de commande pour mettre à jour les mots de passe pour les comptes VmAdmin et DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="8acbd-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8acbd-116">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8acbd-116">Parameters</span></span>
<span data-ttu-id="8acbd-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8acbd-117"></span></span>

|<span data-ttu-id="8acbd-118">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8acbd-118">**Parameter**</span></span>|<span data-ttu-id="8acbd-119">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="8acbd-119">**Required**</span></span>|<span data-ttu-id="8acbd-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="8acbd-120">**Type**</span></span>|<span data-ttu-id="8acbd-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="8acbd-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8acbd-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="8acbd-122">AccountType</span></span> <br/> | <span data-ttu-id="8acbd-123">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="8acbd-123">Required</span></span> <br/> |<span data-ttu-id="8acbd-124">System.String</span><span class="sxs-lookup"><span data-stu-id="8acbd-124">System.String</span></span>  <br/> | <span data-ttu-id="8acbd-125">Valeur du paramètre doit être « TenantAdmin », « VmAdmin » ou « DomainAdmin ».</span><span class="sxs-lookup"><span data-stu-id="8acbd-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8acbd-126">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="8acbd-126">Input Types</span></span>
<span data-ttu-id="8acbd-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8acbd-127"></span></span>

<span data-ttu-id="8acbd-p102">Aucun. L’applet de commande Set-CcCredential n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="8acbd-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8acbd-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="8acbd-130">Return Types</span></span>
<span data-ttu-id="8acbd-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8acbd-131"></span></span>

<span data-ttu-id="8acbd-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="8acbd-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8acbd-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8acbd-133">See also</span></span>
<span data-ttu-id="8acbd-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8acbd-134"></span></span>

[<span data-ttu-id="8acbd-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="8acbd-135">Get-CcCredential</span></span>](get-cccredential.md)
  

