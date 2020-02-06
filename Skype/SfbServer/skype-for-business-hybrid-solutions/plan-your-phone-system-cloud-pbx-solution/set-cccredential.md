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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  '
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824208"
---
# <a name="set-cccredential"></a><span data-ttu-id="b475f-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b475f-103">Set-CcCredential</span></span>
 
<span data-ttu-id="b475f-104">L’applet de commande Set-CcCredential définit les informations du déploiement de la version Cloud Connector de Skype Entreprise.  </span><span class="sxs-lookup"><span data-stu-id="b475f-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="b475f-105">Avec le Cloud Connector version 2,0 et les versions ultérieures, cette applet de contrôle peut également définir les informations de compte de l’administrateur de l’ordinateur virtuel et de l’administrateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="b475f-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="b475f-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="b475f-106">Examples</span></span>
<span data-ttu-id="b475f-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b475f-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b475f-108">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="b475f-108">Example 1</span></span>

<span data-ttu-id="b475f-109">L’exemple suivant spécifie le nom et le mot de passe du compte de l’administrateur de client :</span><span class="sxs-lookup"><span data-stu-id="b475f-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="b475f-110">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="b475f-110">Detailed Description</span></span>
<span data-ttu-id="b475f-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b475f-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="b475f-112">L’applet de commande Set-CcCredential définit le nom et le mot de passe du compte de l’administrateur de client.</span><span class="sxs-lookup"><span data-stu-id="b475f-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="b475f-113">Pour les versions antérieures à 2,0, cet administrateur doit être un administrateur général Office 365.</span><span class="sxs-lookup"><span data-stu-id="b475f-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="b475f-114">Le Cloud Connector utilise ce compte pour obtenir les informations de configuration, définir les paramètres de configuration et mettre à jour l’état de l’appareil sur la configuration du client Office 365.</span><span class="sxs-lookup"><span data-stu-id="b475f-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="b475f-115">Avec la version 2,0 et les versions ultérieures, vous pouvez également utiliser cette applet de cmdlet pour mettre à jour les mots de passe des comptes VmAdmin et DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="b475f-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b475f-116">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b475f-116">Parameters</span></span>
<span data-ttu-id="b475f-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b475f-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="b475f-118">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="b475f-118">**Parameter**</span></span>|<span data-ttu-id="b475f-119">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="b475f-119">**Required**</span></span>|<span data-ttu-id="b475f-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="b475f-120">**Type**</span></span>|<span data-ttu-id="b475f-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="b475f-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b475f-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="b475f-122">AccountType</span></span> <br/> | <span data-ttu-id="b475f-123">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="b475f-123">Required</span></span> <br/> |<span data-ttu-id="b475f-124">System.String</span><span class="sxs-lookup"><span data-stu-id="b475f-124">System.String</span></span>  <br/> | <span data-ttu-id="b475f-125">La valeur du paramètre doit être « TenantAdmin », « VmAdmin » ou « DomainAdmin ».</span><span class="sxs-lookup"><span data-stu-id="b475f-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b475f-126">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="b475f-126">Input Types</span></span>
<span data-ttu-id="b475f-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b475f-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="b475f-p102">Aucun. L’applet de commande Set-CcCredential n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="b475f-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b475f-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="b475f-130">Return Types</span></span>
<span data-ttu-id="b475f-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b475f-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b475f-132">Aucun</span><span class="sxs-lookup"><span data-stu-id="b475f-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b475f-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b475f-133">See also</span></span>
<span data-ttu-id="b475f-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b475f-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="b475f-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b475f-135">Get-CcCredential</span></span>](get-cccredential.md)
  

