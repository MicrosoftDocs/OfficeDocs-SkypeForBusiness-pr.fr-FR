---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande Switch-CcVersion déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup.
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003154"
---
# <a name="switch-ccversion"></a><span data-ttu-id="8183c-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="8183c-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="8183c-104">L’applet de commande Switch-CcVersion déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup.</span><span class="sxs-lookup"><span data-stu-id="8183c-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="8183c-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="8183c-105">Examples</span></span>
<span data-ttu-id="8183c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8183c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8183c-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8183c-107">Example 1</span></span>

<span data-ttu-id="8183c-108">L’exemple suivant drainne les services de l’application en cours d’exécution, puis bascule vers une nouvelle application de déploiement ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="8183c-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="8183c-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="8183c-109">Example 2</span></span>

<span data-ttu-id="8183c-110">L’exemple suivant drainne les services de l’application en cours d’exécution et arrête les services de force en cas d’échec du drainage des services.</span><span class="sxs-lookup"><span data-stu-id="8183c-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="8183c-111">La commande bascule alors vers une nouvelle appliance déployée ou de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="8183c-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="8183c-112">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="8183c-112">Detailed Description</span></span>
<span data-ttu-id="8183c-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8183c-113"></span></span>

<span data-ttu-id="8183c-114">L’applet de connexion Switch-CcVersion draine les services de connecteur Cloud sur le serveur de médiation et le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="8183c-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="8183c-115">Tous les appels en cours seront exécutés, mais les nouveaux appels seront rejetés par l’appliance.</span><span class="sxs-lookup"><span data-stu-id="8183c-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="8183c-116">Après le vidage, l’applet de connexion déconnecte l’application en cours d’exécution des réseaux d’entreprise et Internet, éteint toutes les machines virtuelles appartenant à l’application, puis connecte l’appareil de sauvegarde aux réseaux d’entreprise et Internet.</span><span class="sxs-lookup"><span data-stu-id="8183c-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8183c-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8183c-117">Parameters</span></span>
<span data-ttu-id="8183c-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8183c-118"></span></span>

|<span data-ttu-id="8183c-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="8183c-119">**Parameter**</span></span>|<span data-ttu-id="8183c-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="8183c-120">**Required**</span></span>|<span data-ttu-id="8183c-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="8183c-121">**Type**</span></span>|<span data-ttu-id="8183c-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="8183c-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8183c-123">Force</span><span class="sxs-lookup"><span data-stu-id="8183c-123">Force</span></span> <br/> | <span data-ttu-id="8183c-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="8183c-124">Optional</span></span> <br/> |<span data-ttu-id="8183c-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8183c-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="8183c-126">Arrête les services de force en cas d’échec du drainage des services.</span><span class="sxs-lookup"><span data-stu-id="8183c-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8183c-127">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="8183c-127">Input Types</span></span>
<span data-ttu-id="8183c-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8183c-128"></span></span>

<span data-ttu-id="8183c-129">Aucun</span><span class="sxs-lookup"><span data-stu-id="8183c-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8183c-130">Types de retours</span><span class="sxs-lookup"><span data-stu-id="8183c-130">Return Types</span></span>
<span data-ttu-id="8183c-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8183c-131"></span></span>

<span data-ttu-id="8183c-132">Aucune</span><span class="sxs-lookup"><span data-stu-id="8183c-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8183c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8183c-133">See also</span></span>
<span data-ttu-id="8183c-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8183c-134"></span></span>

<span data-ttu-id="8183c-135">Aucun</span><span class="sxs-lookup"><span data-stu-id="8183c-135">None</span></span>
  

