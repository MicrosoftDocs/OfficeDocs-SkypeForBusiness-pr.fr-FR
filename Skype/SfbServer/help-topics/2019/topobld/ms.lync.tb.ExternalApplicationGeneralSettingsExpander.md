---
title: Expanseur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 8cdf27598c916f84e96b11d8acfaeb115a0575dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822424"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="a9374-103">Expandeur des paramètres généraux d’une application externe</span><span class="sxs-lookup"><span data-stu-id="a9374-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="a9374-104">Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.</span><span class="sxs-lookup"><span data-stu-id="a9374-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="a9374-105">Deux sections peuvent être modifiées :</span><span class="sxs-lookup"><span data-stu-id="a9374-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="a9374-106">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="a9374-106">General settings</span></span>
> 
> <span data-ttu-id="a9374-107">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="a9374-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="a9374-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="a9374-108">General Settings</span></span>

<span data-ttu-id="a9374-p101">Vous pouvez modifier le nom de domaine complet actuel du pool de serveurs d’applications approuvées. Modifiez le nom de domaine complet du pool. Les enregistrements d’hôte DNS (Domain Name System) (A) doivent exister pour la nouvelle entrée pour que les clients ou les serveurs puissent se connecter au nouveau nom de pool.</span><span class="sxs-lookup"><span data-stu-id="a9374-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="a9374-p102">Sélectionnez **Activer la réplication des données de configuration sur ce pool** si les données de configuration doivent être répliquées sur ce pool. Désactivez la case à cocher si vous ne voulez pas répliquer les données de configuration.</span><span class="sxs-lookup"><span data-stu-id="a9374-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="a9374-114">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="a9374-114">Next Hop Settings</span></span>

<span data-ttu-id="a9374-115">Vous pouvez spécifier le serveur du saut suivant du pool de serveurs d’applications approuvé en sélectionnant le pool frontal Enterprise Edition défini ou le serveur frontal Standard Edition dans la liste liste.</span><span class="sxs-lookup"><span data-stu-id="a9374-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="a9374-116">Un directeur ou un pool de directeurs n’est pas un choix valide pour un tronçon suivant de serveur d’applications approuvées et n’apparaîtra pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a9374-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="a9374-117">Cliquez **sur OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="a9374-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="a9374-118">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="a9374-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

